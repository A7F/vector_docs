# tlsGetLastError

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

```
long tlsGetLastError(dword socket);
```

## Description

Returns the **TLS** error code of the last operation that failed on a specified socket.

## Parameters

- **socket**: The socket handle.

## Return Values

- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **Success (0)**: No error occurred.
- **Failed (1)**: General error.
- **InvalidParameter (2)**: A given parameter was invalid.
- **SocketError (3)**: A socket error occurred. Call [IpGetLastSocketError](../../TCPIPAPI/Functions/CAPLfunctionIPGetLastSocketError.md) for details.
- **PeerClosed (4)**: The TLS connection was closed by the peer.
- **IoPending (997)**: The last operation is pending and will complete later.

## Example

```c
void OnTcpListen( dword socket, long result)
{
  DWORD clientHandle;
  // Accept the connection
  clientHandle = TcpAccept( socket );

  tlsOpen(clientHandle);
  tlsAuthenticateAsServer(clientHandle, "Server1");

  if ((tlsGetLastError(clientHandle) != 0) &&
      (tlsGetLastError(clientHandle) != 997))
  {
    // an error occurred
    return;
  }
}
```
