[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDOnError.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783PDDOnError

# Iso11783PDDOnError (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void Iso11783PDDOnError( dword ecuHandle, long errorCode, dword param );
```

## Description

This function can be implemented in the CAPL program. The function is called up by the node layer when an error occurs.

## Parameters

- **ecuHandle**: Handle of the ECU
- **errorCode**: Error code
- **param**: additional parameter, dependent on the [error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Return Values

—

## Example

```plaintext
void Iso11783PDDOnError( LONG ecuHandle, LONG errorCode, LONG addParam )
{
  char buffer[256];
  Iso11783PDDGetLastErrorText ( elCount(buffer), buffer);
  write( "ERROR: %s", buffer );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)