[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionUDPConnect.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » UdpConnect

# UdpConnect

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long udpConnect(dword socket, IP_Endpoint remoteEndpoint);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
long socket.Connect(IP_Endpoint remoteEndpoint);
```

## Description

The function connects this socket to the given remote endpoint. After the socket is connected it is necessary to use [UdpSend](CAPLfunctionUDPSend.md) instead of [UdpSendTo](CAPLfunctionUDPSendTo.md).

On Server side it is possible to connect to the remote endpoint when receiving data the first time on a socket. After that a new unconnected Socket can be created to wait for the next incoming udp connection (see example).

## Parameters

- **socket**: The socket handle.
- **remoteEndpoint**: The destination endpoint. IP address and port number must be specified.

  **Example:**

  - `IP_Endpoint( 192.168.1.1:40001 )`
  - `IP_Endpoint( [FC00::0001]:40001 )`

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code.

## Example

### Client.can

```plaintext
variables
{
  UdpSocket gSocket1;
  UdpSocket gSocket2;
  char gBuffer[1500];
}

on start
{
  gSocket1 = UdpSocket::Open( IP_Endpoint(0.0.0.0:0) );
  gSocket2 = UdpSocket::Open( IP_Endpoint(0.0.0.0:0) );
  gSocket1.Connect(IP_Endpoint(192.168.1.3:40002));
  gSocket2.Connect(IP_Endpoint(192.168.1.3:40002));
}

on key '1'
{
  // send on the connected socket
  SendCommand(gSocket1, "Request");

  // wait for response
  gSocket1.ReceiveFrom(gBuffer, elcount(gBuffer));
}

on key '2'
{
  // send on the connected socket
  SendCommand(gSocket2, "Request");

  // wait for response
  gSocket1.ReceiveFrom(gBuffer, elcount(gBuffer));
}

on key 'c'
{
  SendCommand(gSocket1, "End");
  gSocket1.Close();

  SendCommand(gSocket2, "End");
  gSocket1.Close();
}

SendCommand(UdpSocket socket, char command[])
{
  socket.Send(command, strlen(command));
}

OnUdpReceiveFrom(dword socket, long result, IP_Endpoint remoteEndpoint, char buffer[], dword size)
{
  // handle the response from the server here
}
```

### Server.can

```plaintext
variables
{
  // context to handle the state of the different connections
  struct connectionContext
  {
    int connectionNumber;
  };

  dword gListeningSocket;
  struct connectionContext connections[long];
  char gBuffer[1500];
  dword gConnectionCount;
}

on start
{
  gConnectionCount = 0;
  // open a socket and wait for the first data
  gListeningSocket = UdpOpen( IP_Endpoint(0.0.0.0:40002) );
  UdpReceiveFrom(gListeningSocket, gBuffer, elcount(gBuffer));
}

OnUdpReceiveFrom(dword socket, long result, IP_Endpoint remoteEndpoint, char buffer[], dword size)
{
  if(socket == gListeningSocket)
  {
    // create a context for this connection and open a new socket for the
    // next connection

    UdpConnect(socket, remoteEndpoint);
    connections[socket].connectionNumber = ++gConnectionCount;
    gListeningSocket = UdpOpen( IP_Endpoint(0.0.0.0:40002) );
    UdpReceiveFrom(gListeningSocket, gBuffer, elcount(gBuffer));
  }
  AnswerRequest(socket, buffer, size);
}

AnswerRequest(dword socket, char buffer[], dword size)
{
  char response[100];

  if(strncmp(buffer, "Request", size) == 0)
  {
    snprintf(response, elcount(response), "Response for connection #%d", connections[socket].connectionNumber);
    UdpSend(socket, response, strlen(response));
    UdpReceiveFrom(socket, gBuffer, elcount(gBuffer));
  }
  else if(strncmp(buffer, "End", size) == 0)
  {
    connections.remove(socket);
    UdpClose(socket);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
