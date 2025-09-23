[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPBind.md)

**CAPL Functions** » **TCP/IP API** » **IpBind**

# IpBind

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long IpBind( dword socket, dword address, dword port); // form 1`
- `long IpBind( dword socket, byte ipv6Address[], dword port); // form 2`
- `long IpBind( dword socket, IP_Endpoint localEndpoint ); // form 3`

## Method Syntax

- `socket.Bind( dword address, dword port); // form 1`
- `socket.Bind(byte ipv6address[], dword port); // form 2`
- `socket.Bind( IP_Endpoint localEndpoint ); // form 3`

## Description

The function associates an address and a port with the specified socket, after an unbound socket has been generated with [TcpOpen(0, 0)](CAPLfunctionTCPOpen.md).

Do not use IpBind when you are working with [TcpConnect](CAPLfunctionTCPConnect.md) or [TcpListen](CAPLfunctionTCPListen.md) because these two commands bind the socket implicitly.

## Parameters

- **socket**: The socket handle of the socket to be bound.
- **address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) local IPv4 address.
- **ipv6address**: The local IPv6 address in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **port**: The local port in host-byte order.
- **localEndpoint**: Bind the socket to this local endpoint.
  - IP Address can be 0, if the socket should not be bound to an address.
  - Port number can be undefined, if a dynamic port number should be used.
  - Examples:
    - `IP_Endpoint(192.168.1.1:4000)` – Bind to address and port
    - `IP_Endpoint(0.0.0.0:4000)` – Bind only to port for IPv4
    - `IP_Endpoint([::]:4000)` – Bind only to port for IPv6
    - `IP_Endpoint(192.168.1.1)` – Bind to address and choose a dynamic port

## Return Values

- **0**: The function completed successfully.
- **WSA_INVALID_PARAMETER (87)**: The specified socket was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

## Example

```plaintext
variables
{
  UdpSocket gSocket;
  char gRxBuffer[1000];
}

on start
{
  gSocket = UdpSocket::Open( IP_Endpoint(0.0.0.0) );
}

on key '1'
{
  gSocket.Bind( IP_Endpoint(192.168.0.7:40007) );
  gSocket.SendTo( IP_Endpoint(192.168.0.100:40100), "Hello", 5 );
}
```
