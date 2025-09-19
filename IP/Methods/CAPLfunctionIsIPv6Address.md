[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionIsIPv6Address.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Address::IsIPv6Address

# IP_Address::IsIPv6Address

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
long IP_Address::IsIPv6Address();
```

## Description

Checks if the current address is an IPv6 address.

## Parameters

—

## Return Values

Returns 1 if the object currently represents an IPv6 address.

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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
