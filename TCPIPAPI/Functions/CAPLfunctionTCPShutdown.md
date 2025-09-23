[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionTCPShutdown.md)

**CAPL Functions** » **TCP/IP API** » **TcpShutdown**

# TcpShutdown

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TcpShutdown( dword socket);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
socket.Shutdown( dword socket);
```

## Description

The function disables send operations on the specified socket. This function may be used to shutdown a TCP connection. Data can thereby still be received.

When this function is used the socket (in contrast to [TcpClose](CAPLfunctionTCPClose.md)) is closed **only for the sending direction**.

The remote station is informed about this with event procedure [OnTcpClose](../EventProcedures/CAPLfunctionTCPIPOnTcpClose.md).

**Note**

The remote station cannot recognize whether **TcpClose** or **TcpShutdown** was used. For this reason the application or protocol must clearly control how a node behaves.

An example of a **TcpShutdown** can be a web service. The client sends a request to the server and then immediately closes its connection (in the sending direction). The server recognizes from this that the request is finished and sends the response to the client. The client receives the information on the socket closed in the sending direction and closes the connection with [TcpClose](CAPLfunctionTCPClose.md).

In contrast to this an FTP protocol behaves by using a connection to control a permanent dialog between the nodes. The connection is completely closed by a special termination command.

## Parameters

- **socket**: The socket handle.

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code.

## Example

```plaintext
variables
{
  // error codes:
  const dword SUCCESS = 0;
  const dword WSA_IO_PENDING = 997;
  const dword WSAEWOULDBLOCK = 10035;
  const dword INVALID_SOCKET = ~0;

  // address and port of the server
  ip_Endpoint TCP:192.168.1.3:1234 gServerEndpoint;
  dword gConnection = INVALID_SOCKET;
}

// open a tcp socket and begin to connect it to the server
on start
{
  long result;
  // the connection will be implicit bound to a free port when it gets connected
  gConnection = TcpOpen(ip_Endpoint(0.0.0.0:0));
  if (gConnection == INVALID_SOCKET)
  {
    writeLineEx(1,3,"<%BASE_FILE_NAME%> Failed to open tcp socket. Error: %d", IpGetLastError());
    return;
  }
  result = TcpConnect( gConnection, gServerEndpoint );
  if (result != SUCCESS && IpGetLastSocketError(gConnection) != WSAEWOULDBLOCK )
  {
    write( "<%BASE_FILE_NAME%> TcpConnect failed: (Result %d)", IpGetLastSocketError(gConnection) );
    TcpClose(gConnection);
  }
}

// This callback gets called when the connection is established.
OnTcpConnect(dword socket, long result)
{
  char data[20] = "Hello Server";

  if(result != SUCCESS)
  {
    writeLineEx(1, 3, "<%BASE_FILE_NAME%> Failed to connect tcp socket. Error: %d", result);
    TcpClose(socket);
    return;
  }

  // Start sending some data to the server.
  result = tcpSend(socket, data, strlen(data));
  if (result != SUCCESS && ipGetLastSocketError(socket) != WSA_IO_PENDING )
  {
    write( "<%BASE_FILE_NAME%> TcpSend failed: %s (Result %d)", IpGetLastSocketError(socket) );
    TcpClose(socket);
    return;
  }

  // Prepare socket to receive response.
  result = tcpReceive(socket);
  if (result != SUCCESS && ipGetLastSocketError(socket) != WSA_IO_PENDING )
  {
    write( "<%BASE_FILE_NAME%> TcpReceive failed: %s (Result %d)", IpGetLastSocketError(socket) );
    TcpClose(socket);
    return;
  }

  // Shutdown the connection. It is not possible to send more data after the socket is shutdown. But it
  // is possible to receive data from the server until the server also closes its connection
  result = tcpShutdown(socket);
  if (result != SUCCESS )
  {
    write( "<%BASE_FILE_NAME%> TcpShutdown failed: %s (Result %d)", IpGetLastSocketError(socket) );
    TcpClose(socket);
    return;
  }
}

// receive the answer from the server
OnTcpReceive(dword socket, long result, dword address, dword port, char buffer[], dword size)
{
  if(result == SUCCESS)
  {
    writeLineEx(1, 0, "<%BASE_FILE_NAME%> received: %s", buffer);
  }
}

// close the socket when the server closes the connection
OnTcpClose(dword socket, long result)
{
  TcpClose(socket);
}
```
