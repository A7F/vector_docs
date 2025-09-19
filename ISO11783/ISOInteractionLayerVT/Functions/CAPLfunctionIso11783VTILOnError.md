[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILOnError.md)

# VTIL_OnError (Callback)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_OnError

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void VTIL_OnError( long errorCode, long param );
```

## Description

This callback function is called from the VT IL if an error occurred.

## Parameters

- **errorCode**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **param**: Additional parameter depending on the error code

## Return Values

—

## Example

```plaintext
void VTIL_OnError( long errorCode, long param )
{
  write( "Error %d, parameter %d", errorCode, param );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
