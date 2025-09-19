[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAdapterPrefix.md)

**CAPL Functions** » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAdapterPrefix

# IpGetAdapterPrefix

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetAdapterPrefix(dword ifIndex, dword prefixes[], dword &count);
```

## Description

The function retrieves the address prefixes associated with the specified network interface. The network prefix is a numerical value that specifies the network portion of an IP address.

## Parameters

- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.
- **prefixes**: Address prefixes are copied to this array.
- **count**: The number of prefixes returned by this function.

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
  long addrPrefixes[10];
  dword addrPrefixesCount;
  long addrIdx;
  long ifIdx;

  write("IP Configuration");

  for(ifIdx = 1; ifIdx <= ipGetAdapterCount(); ifIdx++)
  {
    ipGetAdapterAddress(ifIdx, addresses, addressesCount);
    ipGetAdapterMask(ifIdx, addrMasks, addrMasksCount);
    ipGetAdapterPrefix(ifIdx, addrPrefixes, addrPrefixesCount);

    for(addrIdx = 0; addrIdx < addressesCount; addrIdx++)
    {
      char addrStr[30];
      char maskStr[30];
      addresses[addrIdx].PrintAddressToString(addrStr);
      addrMasks[addrIdx].PrintAddressToString(maskStr);

      write(" %d. %s | %s | %ld", addrIdx+1, addrStr, maskStr, addrPrefixes[addrIdx]);
    }
  }
}
```

[IpGetAdapterMask](CAPLfunctionIPGetAdapterMask.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
