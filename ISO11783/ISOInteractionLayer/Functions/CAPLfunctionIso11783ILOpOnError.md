[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOpOnError.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPOnError

# Iso11783IL_OPOnError

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783IL_OPOnError( long error, dword vtFunction );
```

## Description

The function is called by the node layer, when the object pool detects an error.

## Parameters

- **error**: [Error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **vtFunction**: VT function which was executed when the error occurred

## Return Values

—

## Example

```c
void Iso11783IL_OPOnError( LONG error, dword vtFunction )
{
}
```

• Technical References are only available in English

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
