[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionTCPAccept.md)

# TcpAccept

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » TcpAccept

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword TcpAccept( dword socket);
```

## Method Syntax as Constructor

[TcpSocket::Accept( dword socket)](../../../Shared/CAPL/General/ClassesAndObjects.md)

## Description

The function accepts an incoming connection request on the specified socket resulting in a new socket. If the operation fails, the function will return INVALID_SOCKET (~0).

A listen socket created with [TcpListen](CAPLfunctionTCPListen.md) is responded to with callback function [OnTcpListen](../EventProcedures/CAPLfunctionTCPIPOnTcpListen.md) when the connection is established by a client with [TcpConnect](CAPLfunctionTCPConnect.md).

The incoming connection must always be accepted with TcpAccept. That is typically carried out in callback function [OnTcpListen](../EventProcedures/CAPLfunctionTCPIPOnTcpListen.md).

As long as the connection is not accepted, no other clients can be accepted on the listen socket. All other incoming clients then have [error](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md) **10061 (Connection refused)** delivered in callback [OnTcpConnect](../EventProcedures/CAPLfunctionTCPIPOnTcpConnect.md) and can also no longer be accepted subsequently.

Without acceptance of the connection, the system goes to a state in which nothing else happens because no data can be sent and other clients are refused on the listen socket.

There is a queue size for incoming connections in the stack. This is set permanently to 1 in the CANoe DE product so that only one client can be in the queue until it is accepted.

As soon as the connection has been accepted, there is a new socket for the client on which incoming data can be awaited with [TcpReceive](CAPLfunctionTCPReceive.md) and on which data can be sent to the client with [TcpSend](CAPLfunctionTCPSend.md).

## Parameters

- **socket**: The socket handle of the listen socket that was created with [TcpListen](CAPLfunctionTCPListen.md).

## Return Values

- **INVALID_SOCKET (~0)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code. If this error code is WSA_INVALID_PARAMETER (87), the specified socket was invalid. Otherwise, use [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get the reason for the failing.
- **Any other value**: A valid socket handle identifying the created socket.

## Example

```c
// ---------------------------------------------------
// Callback when client connects to server's listen socket.
// ---------------------------------------------------
void OnTcpListen( dword socket, long result)
{
  dword newSocket;
  newSocket = TcpAccept( socket );
  if (newSocket != INVALID_SOCKET)
  {
    // start to receive data on newSocket with TcpReceive...
  }
  else
  {
    writeLineEx( 1, 3, "TcpAccept: Error %d", IpGetLastSocketError(listenSocket));
  }
}
```

[Create TCP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
