[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionTCPIPOnTcpClose.md)

## CAPL Functions » TCP/IP API » OnTcpClose

### Function Syntax

```plaintext
void OnTcpClose( dword socket, long result);
```

### Method Syntax

```plaintext
void OnTcpClose( TcpSocket socket, long result);
```

### Description

If the CAPL program implements this callback it is called when a TCP socket receives a close notification, when the remote station terminates the connection with [TcpClose](../Functions/CAPLfunctionTCPClose.md) or [TcpShutdown](../Functions/CAPLfunctionTCPShutdown.md).

To release the resources of the socket, [TcpClose](../Functions/CAPLfunctionTCPClose.md) must be called.

### Parameters

- **socket**: The socket handle or socket object.
- **result**: The specific result code of the operation. If the operation completed successfully the value is 0. Otherwise the value is an [error code](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md). Typical errors are interrupt of the connection, timeout or reset.

### Return Values

—

### Example

```plaintext
// ---------------------------------------------------
// TCP socket receives a close notification
// ( remote disconnected )
// ---------------------------------------------------

void OnTcpClose( dword socket, long result)
{
  writeLineEx(1, 1, " [ OnTcpClose called. (socket: %d, result: %d) ]", socket, result);
  TcpClose(socket);
}
```

[Create TCP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
