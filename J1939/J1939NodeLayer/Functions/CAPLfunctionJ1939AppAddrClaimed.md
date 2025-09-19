[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939AppAddrClaimed.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939AppAddrClaimed

# J1939AppAddrClaimed (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939AppAddrClaimed( long ecuHandle );
```

## Description

Indicates that Address Claiming was performed successfully, which means that the control device is permitted to communicate on the CAN bus.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

—

## Example

```c
dword J1939AppAddrClaimed( LONG ecuHandle )
{
  /* user code */
  return 0;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
