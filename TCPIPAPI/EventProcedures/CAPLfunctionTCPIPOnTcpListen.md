[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionTCPIPOnTcpListen.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » OnTcpListen

# OnTcpListen

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
void OnTcpListen( dword socket, long result)
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
void OnTcpListen( TcpSocket socket, long result);
```

## Description

If the CAPL program implements this callback it is called when [TcpListen](../Functions/CAPLfunctionTCPListen.md) was called and a connection request for the specified socket is received.

The connection must be accepted with [TcpAccept](../Functions/CAPLfunctionTCPAccept.md) because the listen socket otherwise remains blocked for other clients. This block is evident for a client in [OnTcpConnect](CAPLfunctionTCPIPOnTcpConnect.md) from the output of error code 10061 (Connection refused).

## Parameters

- **socket**: The socket handle or socket object. If the handle is valid (not equal to ~0), it corresponds to the socket that was used for [TcpListen](../Functions/CAPLfunctionTCPListen.md).
- **result**: The specific result code of the operation. If the operation completed successfully the value is zero. Otherwise the value is an [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md).

## Return Values

—

## Example

```c
// ---------------------------------------------------
// Callback when client connects to server's listen socket.
// ---------------------------------------------------
void OnTcpListen( dword socket, long result)
{
  dword newSocket;
  newSocket = TcpAccept( socket );
  if (newSocket != ~0)
  {
    // start to receive data on the new socket...
  }
  else
  {
    writeLineEx( 1, 3, "S: TcpAccept: Socket error: %d", IpGetLastSocketError(socket) );
  }
}
```

[Create TCP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
