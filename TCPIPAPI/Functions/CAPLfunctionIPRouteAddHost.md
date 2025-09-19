[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPRouteAddHost.md)

**CAPL Functions** » **TCP/IP API** » **IPRouteAddHost**

# IPRouteAddHost

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long IPRouteAddHost( dword hostAddr, byte macId[] ); // form 1`
- `long IPRouteAddHost( byte hostAddr[], byte macId[] ); // form 2`
- `long IPRouteAddHost( IP_Address hostAddr, qword macId ); // form 3`

## Description

With this function, it is possible to add a static host route to the routing table of an interface in the TCP/IP stack. When such a route is installed, the TCP/IP stack will no longer perform an ARP request or neighbor solicitation when a message is sent to this destination.

It is necessary that an interface or network route already exists. So the dedicated interface for this route can be found. When there is no interface route found, it is possible to add one with the function [IPRouteAddInterface](CAPLfunctionIPRouteAddInterface.md).

**Example**

The IP address 192.168.1.1/24 is configured on your network adapter. This means an interface route to the network 192.168.1.00/24 is automatically installed on measurement start. So it's possible to add a host route to any address of this network, e.g., 192.168.1.10.

## Parameters

- **hostAddr**: The IPv4 or IPv6 destination address of the route
- **macId**: The mac ID of the host route

## Return Values

- **0**: The function completed successfully.
- **1**: The function is not supported on the selected TCP/IP stack.
- **WSA_INVALID_PARAMETER (87)**: Invalid parameter given
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

## Example

```plaintext
variables
{
  UdpSocket gSocket;
}

on start
{
  ipRouteAddHost( IP_Address(192.168.0.190), ethGetMacAddressAsNumber("02:00:00:00:00:BE") );
  gSocket = UdpSocket::Open( IP_Endpoint(192.168.0.18:40018) );

  // this send request will send the UDP packet to the MAC address,
  // which was configured above, without performing an ARP request.
  gSocket.SendTo( IP_Endpoint(192.168.0.190:40190), "Hello", 5 );
}

on preStop
{
  ipRouteDeleteHost( IP_Address(192.160.0.190) );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
