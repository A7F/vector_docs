[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetLastSocketError.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetLastSocketError

# IpGetLastSocketError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long IpGetLastSocketError( dword socket);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
socket.GetLastSocketError();
```

## Description

The function returns the [Winsock 2 error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md) of the last operation that failed on the specified socket.

## Parameters

- **socket**: The socket handle.

## Return Values

- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **Any other value**: The error code as provided by the Winsock 2 WSAGetLastError function.

## Example

```plaintext
on start
{
  const dword INVALID_SOCKET = ~0; // invalid socket constant
  dword socket = INVALID_SOCKET;   // a socket

  // just create an unspecified socket.
  socket = UdpOpen( 0, 0 );

  // produce an error e.g. using invalid parameters to UdpSendTo
  if (UdpSendTo(socket, 0, 0, "a", 1) == -1)
  {
    writeLineEx(1, 3, "IpGetLastSocketError: %d", IpGetLastSocketError(socket));
  }

  // close the socket.
  UdpClose(socket);
}
```

[IpGetLastError](CAPLfunctionIPGetLastError.md) • [IpGetLastSocketErrorAsString](CAPLfunctionIPGetLastSocketErrorAsString.md)
