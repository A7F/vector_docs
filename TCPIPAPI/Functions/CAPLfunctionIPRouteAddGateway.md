# IPRouteAddGateway

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IPRouteAddGateway

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long IPRouteAddGateway( dword destination, dword mask, dword gateway); // form 1`
- `long IPRouteAddGateway( byte destination[], dword prefix, byte gateway[]); // form 2`
- `long IPRouteAddGateway( IP_Address destination, dword prefix, IP_Address gateway); // form 3`

## Description

With this function, it is possible to add a static gateway route to the routing table in the TCP/IP stack. Depending on the given mask (IPv4) or prefix (IPv6), a route to a single host or to a network is added (see example).

When such a route is installed, the TCP/IP stack will send packets destined to this destination address or network via the given gateway.

## Parameters

- **destination**: The IPv4 or IPv6 destination address of the route.
- **mask**: Mask for the given IPv4 address. If an **all ones mask** is given, a gateway route for a single host is installed. Otherwise, a network gateway route will be installed.
- **prefix**: Prefix for the given IPv6 destination address. If the prefix 128 is given, a gateway route for a single host is installed. Otherwise, a network gateway route will be installed.
- **gateway**: The IPv4 or IPv6 Address of the gateway.

## Return Values

- **0**: The function completed successfully.
- **1**: The function is not supported on the selected TCP/IP stack.
- **WSA_INVALID_PARAMETER (87)**: Invalid parameter given.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

## Example

```plaintext
variables
{
  UdpSocket gSocket;
}

on start
{
  ipRouteAddGateway( IP_Address(192.168.1.0), 24, IP_Address(192.168.0.200) );
  gSocket = UdpSocket::Open( IP_Endpoint(192.168.0.19:40019) );

  // because the destination address of the following send request
  // is in another subnet, the UDP packet will be sent to the
  // MAC address of the gateway which was configured above.
  gSocket.SendTo( IP_Endpoint(192.168.1.123:40123), "Hello", 5 );
}

on preStop
{
  ipRouteDeleteGateway( IP_Address(192.168.1.0), 24 );
}
```
