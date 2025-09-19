[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPLeaveMulticastGroup.md)

**CAPL Functions** » **TCP/IP API** » **IpLeaveMulticastGroup**

# IpLeaveMulticastGroup

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long IpLeaveMulticastGroup( dword socket, dword ifIndex, dword ipv4address ); // form 1`
- `long IpLeaveMulticastGroup( dword socket, dword ifIndex, byte ipv6Address[] ); // form 2`
- `long IpLeaveMulticastGroup( dword socket, dword ifIndex, IP_Address multicastAddress ); // form 3`

## Description

Leaves a previously joined multicast group on the given socket. After that, no multicast messages are received anymore. To receive multicast messages, the multicast group has to be joined with [IpJoinMulticastGroup](CAPLfunctionIPJoinMulticastGroup.md) before. Before multicast messages can be sent, [IpSetMulticastInterface](CAPLfunctionIPSetMulticastInterface.md) has to be called before.

**Note**: The function is dependent on the [selected stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md). This functionality cannot be used in connection with the [operating system TCP/IP stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md).

## Parameters

- **socket**: The socket handle.
- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.
- **ipv4address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) IPv4 address of the destination.
- **ipv6Address**: The local IPv6 address in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **multicastAddress**: The IP multicast address of the destination.

## Return Values

- **0**: The function completed successfully.
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
  gSocket = UdpSocket::Open( IP_Endpoint(0.0.0.0:40001) );
  gSocket.JoinMulticastGroup( 1, IP_Address(239.0.0.123) );
}

on key '2'
{
  gSocket.LeaveMulticastGroup( 1, IP_Address(239.0.0.123) );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
