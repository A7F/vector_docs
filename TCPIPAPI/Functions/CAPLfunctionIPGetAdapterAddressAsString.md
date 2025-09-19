[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAdapterAddressAsString.md)

**CAPL Functions** » **TCP/IP API** » **IpGetAdapterAddressAsString**

# IpGetAdapterAddressAsString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetAdapterAddressAsString( dword ifIndex, char address[], dword count);
```

## Description

The function retrieves the string representation of the first address associated with the specified network interface.

## Parameters

- **ifIndex**: The 1-based network interface index. All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.
- **address**: The buffer used to store the address string in dot notation.
- **count**: The size of the address buffer.

## Return Values

- **0**: The function completed successfully.
- **ERROR_NOT_ENOUGH_MEMORY (8)**: The address buffer was insufficient.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid.
- **WSAEADDRNOTAVAIL (10049)**: No adapter address available.

## Example

```plaintext
on start
{
  const dword IPV4_STR_SIZE = 16; // IPv4 string size
  char ipAddr[IPV4_STR_SIZE];     // human readable ipv4 address string.
  dword ifIdx;                    // interface index
  long result;                    // function result.

  for (ifIdx = 1; ifIdx <= IpGetAdapterCount(); ifIdx++)
  {
    result = IpGetAdapterAddressAsString( ifIdx, ipAddr, elcount(ipAddr) );
    if (result == 0)
    {
      // success.
      write("IpGetAdapterAddressAsString for adapter %d returned: %s", ifIdx, ipAddr);
    }
    else
    {
      writeLineEx(1, 3, "IpGetAdapterAddressAsString: Error %d", result);
      // handle error...
    }
  }
}
```

[IpGetAdapterAddressCount](CAPLfunctionIpGetAdapterAddressCount.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
