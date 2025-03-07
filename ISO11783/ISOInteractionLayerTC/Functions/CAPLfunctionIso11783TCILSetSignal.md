[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILSetSignal.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_SetSignal

# TCIL_SetSignal

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_SetSignal( dbSignal signal, double value ); // form 1
long TCIL_SetSignal( dbNode tc, dbSignal signal, double value ); // form 2
```

## Description

Sets the signal to the specified physical value. The message of the signal is sent according to the configured send type.

## Parameters

- **signal**: Signal name from database. The signal must be assigned to the node as Tx signal.
- **value**: physical value
- **tc**: TC simulation node to apply the function

## Return Values

—

## Example

```plaintext
void SendLanguageCommand_English()
{
  TCIL_SetSignal( LC_TC::LanguageCodeCmd, 0x6E65 );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)