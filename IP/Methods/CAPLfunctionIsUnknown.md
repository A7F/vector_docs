[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionIsUnknown.md)

# IP_Endpoint::IsUnknown

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Endpoint::IsUnknown

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
long IP_Endpoint::IsUnknown();
```

## Description

Checks if the current transport protocol of this endpoint is unknown.

## Parameters

—

## Return Values

Returns 1 if the current transport protocol of this endpoint is unknown.

## Example

```plaintext
on start
{
  IP_Endpoint 192.168.1.1:4000 addr; //neither "UDP:" nor "TCP:" has been specified and thus the transport protocol is unknown
  if (addr.IsUnknown())
  {
    write( "Is endpoint with unknown transport protocol" );
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
