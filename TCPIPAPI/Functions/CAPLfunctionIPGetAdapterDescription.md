[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAdapterDescription.md)

**CAPL Functions** » **TCP/IP API** » **IpGetAdapterDescription**

# IpGetAdapterDescription

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetAdapterDescription( dword ifIndex, char name[], dword count);
```

## Description

The function retrieves the description of the specified network interface.

All adapter addresses including the local loopback address are taken into account in the stack of the operating system. The order depends on how the operating system lists the adapters. All assigned addresses including the VLAN addresses are taken into account in the CANoe DE product stack.

## Parameters

- **ifIndex**: The 1-based network interface index.
- **name**: The buffer used to store the description.
- **count**: The size of the name buffer.

## Return Values

- **0**: The function completed successfully.
- **ERROR_NOT_ENOUGH_MEMORY (8)**: The name buffer was insufficient.
- **WSA_INVALID_PARAMETER (87)**: The specified network interface index was invalid.

## Example

```plaintext
on start
{
  const dword STR_SIZE = 256; // string buffer size
  char ifDescr[STR_SIZE];     // Interface description string.
  dword ifIdx;                // interface index
  long result;                // function result.

  for (ifIdx = 1; ifIdx <= IpGetAdapterCount(); ifIdx++)
  {
    result = IpGetAdapterDescription( ifIdx, ifDescr, elcount(ifDescr) );
    if (result == 0)
    {
      // success.
      write("IpGetAdapterDescription for adapter %d returned: %s", ifIdx, ifDescr);
    }
    else
    {
      writeLineEx(1, 3, "IpGetAdapterDescription: Error %d", result);
    }
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)