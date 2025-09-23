# OnDtlsServerConnect

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnDtlsServerConnect(dword socket, ip_Endpoint endpoint, long result);
```

## Description

If the CAPL program implements this callback it is called on the DTLS server side when a DTLS client begins its TLS handshake.

When a DTLS client begins its handshake the server calls internally [UdpConnect](../../TCPIPAPI/Functions/CAPLfunctionUDPConnect.md) on the listening socket. After the socket is connected to the clients address the callback gets called to inform the user that a new socket for incoming DTLS connections has to be created.

## Parameters

- **socket**: The socket which is now connected to the client.
- **endpoint**: The address and port to which this socket is now connected.
- **result**: The result of the internal call to [UdpConnect](../../TCPIPAPI/Functions/CAPLfunctionUDPConnect.md).

## Return Values

—

## Example

### dtlsClient.can

```plaintext
variables
{
  char data[1500];
}

on start
{
  dword socket;
  socket = UdpOpen(ip_Endpoint(0.0.0.0:0));
  UdpConnect(socket, ip_Endpoint(192.168.1.2:4433));
  socket = TlsOpen(socket);
  tlsAuthenticateAsClient(socket, "Server1");
}

void OnTlsHandshakeComplete(dword socket, long result)
{
  if(result == 0)
  {
    udpSend(socket, "Request", 7);
    udpReceiveFrom(socket, data, elcount(data));
  }
}

OnUdpReceiveFrom(dword socket, long result, dword address, dword port, char buffer[], dword size)
{
  // handle response
  // ...
  write("%BASE_FILE_NAME%: received: %s", buffer);
  tlsClose(socket, 1);
}
```

### dtlsServer.can

```plaintext
variables
{
  dword listeningSocket;
  char data[1500];
}

on start
{
  DtlsListen(ip_Endpoint(0.0.0.0:4433));
}

// create new socket to listen for next connection
void DtlsListen(ip_Endpoint endpoint)
{
  listeningSocket = UdpOpen(endpoint);
  listeningSocket = tlsOpen(listeningSocket);
  tlsAuthenticateAsServer(listeningSocket, "Server1");
}

void OnDtlsServerConnect(dword socket, ip_Endpoint endpoint, long result)
{
  if(result == 0)
  {
    DtlsListen(ip_Endpoint(0.0.0.0:4433));
  }
}

void OnTlsHandshakeComplete(dword socket, long result)
{
  if(result != 0)
  {
    write("%BASE_FILE_NAME%: Tls Handshake failed on socket %d. Socket gets closed. Result: %d", socket, result);
    udpClose(socket);
  }
  else
  {
    write("%BASE_FILE_NAME%: Tls Handshake complete on socket %d. Result: %d", socket, result);
    udpReceiveFrom(socket, data, elcount(data));
  }
}

OnUdpReceiveFrom(dword socket, long result, ip_Endpoint endpoint, char buffer[], dword size)
{
  write("%BASE_FILE_NAME%: received: %s", buffer);
  strncpy(data, buffer, elcount(data));
  strncat(data, " reflected", elcount(data));
  UdpSend(socket, data, strlen(data)); // reflect data
  tlsClose(socket, 1);
}
```
