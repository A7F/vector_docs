[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionTCPClose.md)

**CAPL Functions** » **TCP/IP API** » **TcpClose**

# TcpClose

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TcpClose( dword socket);
```

## Method Syntax as Constructor

```
socket.close();
```

## Description

The function closes the TCP socket. Upon successful completion the passed socket is no longer valid.

In contrast to [TcpShutdown](CAPLfunctionTCPShutdown.md) the connection in each direction is closed and the resources for the socket in the stack are released.

As soon as the socket has been successfully closed, an [OnTcpClose](../EventProcedures/CAPLfunctionTCPIPOnTcpClose.md) event is initiated once on the remote station.

## Parameters

- **socket**: The socket to be closed.

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

## Example

```c
void disconnectSocket( dword socket )
{
  if (socket != -1)
  {
    TcpClose(socket);
  }
}
```

[Create TCP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
