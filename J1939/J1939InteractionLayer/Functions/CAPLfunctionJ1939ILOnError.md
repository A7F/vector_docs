[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILOnError.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILOnError

# J1939ILOnError (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void J1939ILOnError( long errorCode, long param )
```

## Description

This callback function is called from the J1939 IL if an error occurred.

## Parameters

- **errorCode**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **param**: additional parameter depending on the error code

## Return Values

—

## Example

```c
void J1939ILOnError( LONG errorCode, LONG param )
{
  write( "Error %d, parameter %d", errorCode, param );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
