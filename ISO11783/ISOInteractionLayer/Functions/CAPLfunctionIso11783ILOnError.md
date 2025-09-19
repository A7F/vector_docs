[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOnError.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OnError

# Iso11783IL_OnError (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783IL_OnError( long errorCode, long param );
```

## Description

This callback function is called from the ISO11783 IL if an error occurred.

## Parameters

- **errorCode**: [Error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **param**: Additional parameter depending on the error code

## Return Values

—

## Example

```c
void Iso11783IL_OnError( LONG errorCode, LONG param )
{
  write( "Error %d, parameter %d", errorCode, param );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
