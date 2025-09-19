[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionIsIPv4Address.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Address::IsIPv4Address

# IP_Address::IsIPv4Address

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
long IP_Address::IsIPv4Address();
```

## Description

Checks if the current address is an IPv4 address.

## Parameters

—

## Return Values

Returns 1 if the object currently represents an IPv4 address.

## Example

```plaintext
on start
{
  DoSomething( IP_Address(192.168.1.2) );
}

void DoSomething( IP_Address addr )
{
  if (addr.IsIPv4Address())
  {
    // ...
  }
  else if (addr.IsIPv6Address())
  {
    // ...
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
