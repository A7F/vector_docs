[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimOnError.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMOnError

# Iso11783IL_TIMOnError

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void Iso11783IL_TIMOnError(long errorCode, dword addParam)
```

## Description

This callback function is called from the ISO11783 IL if an error occurred while TIM nodes are simulated.

## Parameters

- **errorCode**: Current [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md).
- **addParam**: Additional parameter depending on the error code.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
void Iso11783IL_TIMOnError( long errorCode, dword addParam )
{
  char buffer[256];
  Iso11783IL_GetLastErrorText ( elCount(buffer), buffer);
  write( "Iso11783IL_TIMOnError: Error %i (%f): %s", errorCode,timeNowFloat()/100000.0, buffer );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
