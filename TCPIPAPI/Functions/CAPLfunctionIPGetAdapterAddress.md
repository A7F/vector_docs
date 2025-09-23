[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAdapterAddress.md)

**CAPL Functions** » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAdapterAddress

# IpGetAdapterAddress

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long IpGetAdapterAddress( dword ifIndex, dword ipv4address[],dword ipv4AddressSize); // form 1: deprecated`
- `long IpGetAdapterAddress( dword ifIndex, byte ipv6Addresses[][], dword ipv6AddressesSize); // form 2: deprecated`
- `long IpGetAdapterAddress( dword ifIndex, IP_Address addresses[], dword &count ); // form 3`

## Description

The function retrieves the addresses associated with a network interface. The interface is specified by its 1-based index in the list of network interfaces, i.e., the first interface has index 1.

All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.

## Parameters

- **ifIndex**: The 1-based network interface index.
- **ipv4address**: The array used to store the [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) IPv4 addresses.
- **ipv6Addresses**: The array used to store the IPv6 addresses as [16 byte arrays](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- **ipv4AddressSize**: The size of the address array in number of addresses. E.g., for `long ipv4Addresses[10];` the passed size should be 10.
- **ipv6AddressSize**: The size of the address array in number of addresses. As the second dimension is always expected to be 16 bytes, the given size describes the first dimension of the array only. E.g., for `byte ipv6Addresses[10][16];` the passed size should be 10.
- **count**: Number of IP addresses, which were copied to addresses.
- **addresses**: Array of IP_Address elements, which is filled with the configured IP addresses of the specified interface.

## Return Values

- **0**: The function completed successfully.
- **ERROR_NOT_ENOUGH_MEMORY (8)**: The address array was insufficient.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid.
- **WSAEADDRNOTAVAIL (10049)**: No adapter address available.

## Example

```plaintext
on start
{
  IP_Address addresses[10];
  dword addressesCount;
  IP_Address addrMasks[10];
  dword addrMasksCount;
  long addrIdx;
  long ifIdx;

  write( "IP Configuration" );

  for( ifIdx = 1; ifIdx <= ipGetAdapterCount(); ifIdx++)
  {
    ipGetAdapterAddress( ifIdx, addresses, addressesCount );
    ipGetAdapterMask( ifIdx, addrMasks, addrMasksCount );
    for( addrIdx = 0; addrIdx < addressesCount; addrIdx++ )
    {
      char addrStr[30];
      char maskStr[30];
      addresses[addrIdx].PrintAddressToString( addrStr );
      addrMasks[addrIdx].PrintAddressToString( maskStr );

      write( "  %d. %s | %s", addrIdx+1, addrStr, maskStr );
    }
  }
}
```
