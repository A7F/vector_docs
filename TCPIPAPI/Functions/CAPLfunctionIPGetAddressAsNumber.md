[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAddressAsNumber.md)

**CAPL Functions** » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAddressAsNumber

# IpGetAddressAsNumber

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword IpGetAddressAsNumber( char address[]);
```

## Description

The function converts an IPv4 address string in dot notation to its numerical value in [network-byte order](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).

## Parameters

- **address**: The [numerical](../../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) IPv4 address to be converted.

## Return Values

- **4294967295 (0xFFFFFFF, the equivalent of "255.255.255.255")**: The specified address string was invalid.
- **Any other value**: The numeric equivalent of the given IPv4 address string.

## Example

```plaintext
on start
{
  const dword IPV4_STR_SIZE = 16;   // IPv4 string size
  char ipv4AddrStr[IPV4_STR_SIZE] = "129.168.111.222";

  write("Converting IPv4 Address %s to numerical value => 0x%x", ipv4AddrStr, IpGetAddressAsNumber(ipv4AddrStr));
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
