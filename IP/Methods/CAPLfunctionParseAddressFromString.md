[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionParseAddressFromString.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **IP_Address::ParseAddressFromString**

# IP_Address::ParseAddressFromString

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
long IP_Address::ParseAddressFromString(char ipAddr[]);
```

## Description

Converts the character string to an IPv4 or IPv6 address and sets this address to the IP address value.

## Parameters

- **ipAddr**: A character string representing an IPv4 or IPv6 address.

## Return Values

- **0**: Success
- **1**: Parser error

## Example

```plaintext
on start
{
  IP_Address addr;
  if (addr.ParseAddressFromString( "192.168.1.1" ) == 0)
  {
    // do something with addr
  }
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
