# IPRouteAddInterface

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IPRouteAddInterface

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

- `long IPRouteAddInterface( dword destination, dword mask, dword ifIndex); // form 1`
- `long IPRouteAddInterface( byte destination[], dword prefix, dword ifIndex); // form 2`
- `long IPRouteAddInterface(IP_Address destination, dword prefix, dword ifIndex); // form 3`

## Description

With this function, it is possible to add a static route to an interface to the routing table in the TCP/IP stack. Depending on the given mask (IPv4) or prefix (IPv6), a route to a single host or to a network is added (see example).

When such a route is installed, the TCP/IP stack will send packets destined to this destination on the given interface.

## Parameters

- **destination**: The IPv4 or IPv6 destination address of the route.
- **mask**: Mask for the given IPv4 address. If an **all ones mask** is given, an interface route for a single host is installed. Otherwise, a network interface route will be installed.
- **prefix**: Prefix for the given IPv6 destination address. If the prefix 128 is given, an interface route for a single host is installed. Otherwise, a network interface route will be installed.
- **ifIndex**: The index of the interface for this route.

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
  ipRouteAddInterface( IP_Address(192.168.100.0), 24, 2 );
  gSocket = UdpSocket::Open( IP_Endpoint(192.168.0.20:40020) );

  // because the destination address of the following send request
  // is in another subnet, the UDP packet will be sent over
  // the interface which was configured above.
  gSocket.SendTo( IP_Endpoint(192.168.100.100:40100), "Hello", 5 );
}

on preStop
{
  ipRouteDeleteInterface( IP_Address(192.168.1.0), 24 );
}
```
