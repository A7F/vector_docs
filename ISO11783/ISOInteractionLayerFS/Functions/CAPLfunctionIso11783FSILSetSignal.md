[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILSetSignal.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_SetSignal

# FSIL_SetSignal

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_SetSignal( dbSignal signal, double value ); // form 1
long FSIL_SetSignal( dbNode fs, dbSignal signal, double value ); // form 2
```

## Description

Sets the signal to the specified physical value. The message of the signal is sent according to the configured send type.

## Parameters

- **signal**: Signal name from database. The signal must be assigned to the node as Tx signal.
- **value**: physical value
- **fs**: FS simulation node to apply the function

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
void SendLanguageCommand_English()
{
  FSIL_SetSignal( LC_FS::LanguageCodeCmd, 0x6E65 );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
