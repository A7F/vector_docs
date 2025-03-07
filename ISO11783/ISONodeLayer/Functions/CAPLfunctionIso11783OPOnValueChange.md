[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPOnValueChange.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPOnValueChange

# Iso11783OPOnValueChange (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
void Iso11783OPOnValueChange( dword ecuHandle, dword objectID );
```

## Description

The function is called by the node layer, if the value of an object is changed (with the command Change String Value or Change Numeric Value). The functions [Iso11783OPGetStringValue](CAPLfunctionIso11783OPGetStringValue.md) and [Iso11783OPGetNumericValue](CAPLfunctionIso11783OPGetNumericValue.md) can be used to get the new value of the object.

## Parameters

- **ecuHandle**: Handle of the ECU
- **objectID**: Object Identifier of the changed object

## Return Values

—

## Example

```c
void Iso11783OPOnValueChange( dword handle, dword objectID )
{
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)