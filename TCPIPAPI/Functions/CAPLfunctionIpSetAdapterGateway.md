[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpSetAdapterGateway.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpSetAdapterGateway

# IpSetAdapterGateway

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long IpSetAdapterGateway (dword ifIndex, dword ipv4address); // form 1`
- `long IpSetAdapterGateway (dword ifIndex, byte ipv6Address[]); // form 2`
- `long IpSetAdapterGateway (dword ifIndex, IP_Address address); // form 3`

## Description

The function sets the default gateway address. There can only be one default gateway. An old default gateway address will be overwritten. The default gateway has to be in one of the subnets configured in the network stack, otherwise the network stack will not be able to find a route to the gateway. To remove the gateway, set the address 0.0.0.0 (IPv4) or :: (IPv6).

**Note**: The function is dependent on the [selected stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md). This functionality cannot be used in connection with the [operating system TCP/IP stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md).

## Parameters

- **ifIndex**: The 1-based network interface index. Although you set the default gateway on a defined interface, it is valid for the whole network stack. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.

- **ipv4address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) IPv4 address for the gateway.

- **ipv6Address**: The IPv6 address for the gateway in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).

- **address**: IP address for the gateway.

## Return Values

- **0**: The function completed successfully.
- **1**: The function is not supported on the selected TCP/IP stack.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastError](CAPLfunctionIPGetLastError.md) to get a more specific error code.

## Example

```plaintext
variables
{
  UdpSocket gSocket;
}

on start
{
  ipSetAdapterGateway( 1, IP_Address(192.168.0.200) );
  gSocket = UdpSocket::Open( IP_Endpoint(192.168.0.17:40017) );

  // this send call to another sub-net will request the MAC address
  // of the gateway and sent the UDP packet to the MAC address of the gateway.
  gSocket.SendTo( IP_Endpoint(192.168.1.100:40100), "Hello", 5 );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
