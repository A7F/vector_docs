[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionIsUDP.md)

# IP_Endpoint::IsUDP

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » IP_Endpoint::IsUDP

**Valid for**: CANoe DE • CANoe4SW DE

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
long IP_Endpoint::IsUDP();
```

## Description

Checks if the current transport protocol of this endpoint is UDP.

## Parameters

—

## Return Values

Returns 1 if the current transport protocol of this endpoint is UDP.

## Example

```plaintext
on start
{
  IP_Endpoint UDP:192.168.1.1:4000 addr;
  if (addr.IsUDP())
  {
    write( "Is UDP endpoint" );
  }
  else if (addr.IsTCP())
  {
    write( "Is TCP endpoint" );
  }
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
