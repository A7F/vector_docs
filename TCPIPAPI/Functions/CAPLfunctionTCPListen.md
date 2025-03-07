[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionTCPListen.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » TcpListen

# TcpListen

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TcpListen( dword socket);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
socket.Listen();
```

## Description

The function causes the socket to listen for incoming connection requests, which will be provided in the CAPL callback [OnTcpListen](../EventProcedures/CAPLfunctionTCPIPOnTcpListen.md), if it is implemented in the same CAPL program. If the operation fails, the function will return SOCKET_ERROR (-1). Use [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code.

The socket must have been opened beforehand with [TcpOpen](CAPLfunctionTCPOpen.md) and be bound at least to one port. The binding to the port is carried out during opening or using [IpBind](CAPLfunctionIPBind.md).

The additional binding to an IP address is optional.

Incoming connections on the listen socket must be accepted with [TcpAccept](CAPLfunctionTCPAccept.md) because all other connections will otherwise be refused with error **10061 (Connection refused)**.

## Parameters

- **socket**: The socket handle.

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code.

## Example

```c
// ---------------------------------------------------
// start server
// ---------------------------------------------------
void serverStart()
{
  listenSocket = TcpOpen(0, listenPort);
  if (listenSocket != ~0)
  {
    if (TcpListen( listenSocket ) == 0)
    {
      // success…
    }
    else
    {
      writeLineEx(1, 3, "   [ TcpListen: Error listening on socket. ]");
      TcpClose(listenSocket);
      listenSocket = ~0;
    }
  }
  else
  {
    writeLineEx( 1, 3, "   [ TcpOpen: Error opening TCP Socket on port %d. (Error %d) ]", listenPort, IpGetLastError() );
  }
}
```

[Create TCP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)