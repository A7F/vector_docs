[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAdapterMaskAsString.md)

**CAPL Functions** » **TCP/IP API** » **IpGetAdapterMaskAsString**

# IpGetAdapterMaskAsString

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long IpGetAdapterMaskAsString( dword ifIndex, char mask[], dword count);
```

## Description

The function retrieves the string representation of the first address mask associated with the specified network interface.

## Parameters

- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.

- **mask**: The buffer used to store the address mask string in dot notation.

- **count**: The size of the mask buffer.

## Return Values

- **0**: The function completed successfully.
- **ERROR_NOT_ENOUGH_MEMORY (8)**: The mask buffer was insufficient.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid.
- **WSAEADDRNOTAVAIL (10049)**: No adapter address available.

## Example

```plaintext
on start
{
  const dword IPV4_STR_SIZE = 16;  // IPv4 string size
  dword ifIdx;                    // interface index
  long result;                    // function result.
  char ipv4AdrStr[IPV4_STR_SIZE]; // human readable IPv4 address string
  char ipv4MaskStr[IPV4_STR_SIZE];// human readable IPv4 address mask string

  for (ifIdx = 1; ifIdx <= IpGetAdapterCount(); ifIdx++)
  {
    IpGetAdapterAddressAsString(ifIdx, ipv4AdrStr, elcount(ipv4AdrStr));
    result = IpGetAdapterMaskAsString(ifIdx, ipv4MaskStr, elcount(ipv4MaskStr));
    if (result == 0)
    {
      // success.
      write("IpGetAdapterMask first IP %s of adapter with index %d has mask %s", ipv4AdrStr, ifIdx, ipv4MaskStr);
    }
    else
    {
      writeLineEx(1, 3, "IpGetAdapterMask: Error %d", result);
    }
  }
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
