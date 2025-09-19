[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPRouteDeleteGateway.md)

**CAPL Functions** » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IPRouteDeleteGateway

# IPRouteDeleteGateway

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long IPRouteDeleteGateway( dword dest, dword mask ); // form 1`
- `long IPRouteDeleteGateway( byte dest[], dword prefix ); // form 2`
- `long IPRouteDeleteGateway(IP_Address destination, dword prefix ); // form 3`

## Description

With this function, it is possible to delete a gateway route from the routing table in the TCP/IP stack. Depending on the given mask (IPv4) or prefix (IPv6), a route to a single host or to a network is deleted.

## Parameters

- **destination**: The IPv4 or IPv6 destination address of the route.
- **mask**: Mask for the given IPv4 address.
- **prefix**: Prefix for the given IPv6 destination address.

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
  // is in another sub-net, the UDP packet will be sent to the
  // MAC address of the gateway which was configured above.
  gSocket.SendTo( IP_Endpoint(192.168.1.123:40123), "Hello", 5 );
}

on preStop
{
  ipRouteDeleteGateway( IP_Address(192.168.1.0), 24 );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
