[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpAddAdapterAddress.md)

**CAPL Functions** » **TCP/IP API** » **IpAddAdapterAddress**

# IpAddAdapterAddress

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long IpAddAdapterAddress(dword ifIndex, dword ipv4address, dword ipv4mask); // form 1`
- `long IpAddAdapterAddress(dword ifIndex, byte ipv6Address[], dword prefix); // form 2`
- `long IpAddAdapterAddress(dword ifIndex, IP_Address address, dword prefix ); // form 3`

## Description

The function adds an address to the network interface with the given index.

**Note**: The function is dependent on the [selected stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md). This functionality cannot be used in connection with the [operating system TCP/IP stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md).

## Parameters

- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.
- **ipv4address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) IPv4 address to add to the interface.
- **ipv6Address**: The IPv6 address in [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **ipv4mask**: The IPv4 network mask in network byte order.
- **prefix**: The IPv6 prefix for the given IPv6 address.
- **address**: IP Address to add to the interface.
- **mask**: The network mask as address.

## Return Values

- **0**: The function completed successfully.
- **1**: The function is not supported on the selected TCP/IP stack.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid.
- **SOCKET_ERROR (-1)**: The function failed. Call [IpGetLastSocketError](CAPLfunctionIPGetLastSocketError.md) to get a more specific error code.

## Example

```plaintext
variables
{
  UdpSocket gSocket;
}

on start
{
  ipAddAdapterAddress( 1, IP_Address( 192.168.0.116 ), 24 );
  gSocket = UdpSocket::Open( IP_Endpoint(192.168.0.116:40016) );
  gSocket.SendTo( IP_Endpoint(192.168.0.255:40255), "Hello", 5 );
}

on preStop
{
  ipRemoveAdapterAddress( 1, IP_Address( 192.168.0.116 ), 24 );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)