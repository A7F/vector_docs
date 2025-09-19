[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionTCPConnect.md)

**CAPL Functions** » **TCP/IP API** » **TcpConnect**

# TcpConnect

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long TcpConnect( dword socket, dword address, dword port); // form 1`
- `long TcpConnect( dword socket, byte ipv6Address[], dword port); // form 2`
- `long TcpConnect( dword socket, IP_Endpoint remoteEndpoint ); // form 3`

## Method Syntax

- `socket.Connect( dword address, dword port); // form 1`
- `socket.Connect( byte ipv6Address[], dword port); // form 2`
- `socket.Connect( IP_Endpoint remoteEndpoint ); // form 3`

## Description

The function establishes a connection with the specified location.

Use [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code. The specific error code is WSAWOULDBLOCK (10035), which is not a "real" error but confirms the non-blocking socket behavior. A real connection error is different from [error 10035](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md).

The CAPL callback [OnTcpConnect](../EventProcedures/CAPLfunctionTCPIPOnTcpConnect.md) will be called on completion (successful or not), provided it is implemented in the same CAPL program.

On the remote station [OnTcpListen](../EventProcedures/CAPLfunctionTCPIPOnTcpListen.md) is called up, which accepts the connection with [TcpAccept](CAPLfunctionTCPAccept.md).

## Parameters

- **socket**: The socket handle.
- **address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) IPv4 address of the destination.
- **ipv6Address**: The numerical IPv6 address of the destination in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **port**: The port of the destination in host-byte order.
- **remoteEndpoint**: The destination endpoint. IP address and port number must be specified.

  Example:
  - `IP_Endpoint( 192.168.1.1:40001 )`
  - `IP_Endpoint( [FC00::0001]:40001 )`

## Return Values

- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: Call [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code. If the error code is different from [10035](../CAPLfunctionsTCPIPWinsock2ErrorCodes.md) this indicates a connection error.

## Example

```c
// ---------------------------------------------------
// connect a client...
// ---------------------------------------------------
void clientConnect()
{
  dword result;
  clientSocket = TcpOpen( 0, 0 );
  if (clientSocket != INVALID_SOCKET)
  {
    result = TcpConnect( clientSocket, ipv4Addr[0], listenPort );
    if ( result == -1)
    {
      result = IpGetLastSocketError(clientSocket);
      if ( result != 10035)
      {
        writeLineEx( 1, 3, " [ TcpConnect for client failed with error %d ]", result );
      }
    }
    else
    {
      writeLineEx(1, 3, " [ TcpConnect error %d ]", result);
    };
  }
  else
  {
    writeLineEx(1, 3, " [ TcpOpen: FAILED. ]");
  }
}
```

[Create TCP Client and Server Sockets](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
