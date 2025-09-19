[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783AppAddrClaimed.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783AppAddrClaimed

# Iso11783AppAddrClaimed (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783AppAddrClaimed( long ecuHandle );
```

## Description

Indicates that Address Claiming was performed successfully, which means that the control device is permitted to communicate on the CAN bus.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

—

## Example

```c
dword Iso11783AppAddrClaimed( LONG ecuHandle )
{
  /* user code */
  return 0;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
