[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDOnError.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDOnError

# Iso11783IL_PDDOnError (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void Iso11783IL_PDDOnError( long errorCode, dword param );
```

## Description

This function can be implemented in the CAPL program. The function is called up by the interaction layer when an error occurs.

## Parameters

- **errorCode**: [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **param**: additional parameter, dependent on the error code

## Return Values

—

## Example

```plaintext
void Iso11783IL_PDDOnError( LONG errorCode, LONG addParam )
{
  char buffer[256];
  Iso11783IL_GetLastErrorText ( elCount(buffer), buffer);
  write( "ERROR: %s", buffer );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
