# TCPGetRemoteAddress

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `dword TcpGetRemoteAddress(dword socket); // form 1`
- `dword TCPGetRemoteAddress(dword socket, byte remoteIpv6Address[]); // form 2`
- `long TcpGetRemoteAddress(dword socket, IP_Address &address): // form 3`

## Description

This function retrieves the remote IPv4 address of the specified [connected socket](../../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md).

## Parameters

- **socket**: The socket handle.
- **remoteIpv6Address**: The container for the remote IPv6 address in a [16 byte array](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **address**: IP_Address which returns the IP address.

## Return Values

The IPv4 address of the remote host in [network-byte order](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).

## Example

—

[TcpAccept](CAPLfunctionTCPAccept.md) • [TcpConnect](CAPLfunctionTCPConnect.md)
