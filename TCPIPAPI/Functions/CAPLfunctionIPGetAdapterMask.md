[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAdapterMask.md)

**CAPL Functions** » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAdapterMask

# IpGetAdapterMask

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long IpGetAdapterMask( dword ifIndex, dword mask[], dword maskSize); // form 1`
- `long IpGetAdapterMask( dword ifIndex, IP_Address addressMasks[], dword &count); // form 2`

## Description

The function retrieves the address masks (subnet masks) associated with the specified network interface.

## Parameters

- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.
- **maskSize**: The size of the mask array.
- **count**: The size of the mask array.
- **mask**: The array used to store the [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) IPv4 address masks.
- **addressMasks**: Address masks are copied to this array.

## Return Values

- **0**: The function completed successfully.
- **ERROR_NOT_ENOUGH_MEMORY (8)**: The mask array was insufficient.
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

[IpGetAdapterPrefix](CAPLfunctionIPGetAdapterPrefix.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
