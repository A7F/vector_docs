[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionPrintAddressToString.md)

## IP_Address::PrintAddressToString

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Address::PrintAddressToString

### Method Syntax

`long IP_Address::PrintAddressToString(char ipAddr[]);`

### Description

Converts the IP address to a character string. In case of an IPv6 address the compressed IPv6 address notation is used. In this form the longest row of zeros will be replaced by two colons.

If the scope id in an IPv6 address is set to a value different than zero the address will be converted to the following form: `<ipv6 address>%<scope id>`

This scope ID should be set to the interface index in link local addresses.

**Examples**:

- IPv4 Address: 192.168.1.1
- IPv6 Address: 2001:DB8::1
- IPv6 Address with scope id: 2001:DB8::1%1

### Parameters

- **ipAddr**: String buffer where the string representing an IPv4 or IPv6 address is printed to.

### Return Values

- **0**: Success
- **1**: Character string too small
- **2**: Object has not been set to a valid address

### Example

```plaintext
on start
{
  IP_Address 192.168.1.1 addr;
  char addrStr[20];
  if (addr.PrintAddressToString( addrStr ) == 0)
  {
    write( "Address is %s", addrStr );
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)