# TcpAbort

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionTCPAbort.md)

**CAPL Functions** » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » TcpAbort

---

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TcpAbort( dword socket);
```

## Method Syntax as Constructor

```plaintext
socket.Abort( dword socket);
```

## Description

The function closes the TCP socket immediately and sends a reset flag (RST) to the remote socket. The aborted socket is no longer valid.

In contrast to [TcpClose](CAPLfunctionTCPClose.md) and [TcpShutdown](CAPLfunctionTCPShutdown.md), the connection is not closed by the regular FIN-ACK handshake.

The [OnTcpClose](../EventProcedures/CAPLfunctionTCPIPOnTcpClose.md) callback will be called on the remote socket.

## Parameters

- **socket**: The socket handle.

## Return Values

- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call IpGetLastError to get a more specific error code.

## Example

—

[Create TCP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

---

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
