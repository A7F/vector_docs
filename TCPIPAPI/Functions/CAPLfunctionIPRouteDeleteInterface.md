[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPRouteDeleteInterface.md)

**CAPL Functions** » **TCP/IP API** » **IPRouteDeleteInterface**

# IPRouteDeleteInterface

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long IPRouteDeleteInterface( dword dest, dword mask ); // form 1`
- `long IPRouteDeleteInterface( byte dest[], dword prefix ); // form 2`
- `long IPRouteDeleteInterface( IP_Address destination, dword prefix ); // form 3`

## Description

With this function, it is possible to delete a route to an interface from the routing table in the TCP/IP stack.

## Parameters

- **destination**: The IPv4 or IPv6 destination address of the route.
- **mask**: Mask for the given IPv4 address. If an **all ones mask** is given, an interface route for a single host is installed. Otherwise, a network interface route will be installed.
- **prefix**: Prefix for the given IPv6 destination address. If the prefix 128 is given, an interface route for a single host is installed. Otherwise, a network interface route will be installed.

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
  // is in another sub-net, the UDP packet will be sent over
  // the interface which was configured above.
  gSocket.SendTo( IP_Endpoint(192.168.100.100:40100), "Hello", 5 );
}

on preStop
{
  ipRouteDeleteInterface( IP_Address(192.168.1.0), 24 );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
