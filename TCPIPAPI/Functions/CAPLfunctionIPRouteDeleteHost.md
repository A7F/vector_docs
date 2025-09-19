[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPRouteDeleteHost.md)

# IPRouteDeleteHost

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IPRouteDeleteHost

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long IPRouteDeleteHost( dword hostAddr ); // form 1`
- `long IPRouteDeleteHost( byte hostAddr[] ); // form 2`
- `long IPRouteDeleteHost( IP_Address hostAddr ); // form 3`

## Description

With this function, it is possible to delete a host route from the routing table of an interface in the TCP/IP stack. It is necessary that an interface or network route already exists so the dedicated interface for this route can be found.

## Parameters

- **hostAddr**: The IPv4 or IPv6 destination address of the route.

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

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
