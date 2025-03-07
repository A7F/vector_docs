[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILSetSignal.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_SetSignal

# VTIL_SetSignal

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_SetSignal( dbSignal signal, double value ); // form 1`
- `long VTIL_SetSignal( dbNode vt, dbSignal signal, double value ); // form 2`

## Description

Sets the signal to the specified physical value. The message of the signal is sent according to the configured send type.

## Parameters

- **signal**: Signal name from database. The signal must be assigned to the node as Tx signal.
- **value**: physical value
- **vt**: VT simulation node to apply the function

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example form 1**

```plaintext
void SendLanguageCommand_English()
{
  VTIL_SetSignal( LC_VT::LanguageCodeCmd, 0x6E65 );
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)