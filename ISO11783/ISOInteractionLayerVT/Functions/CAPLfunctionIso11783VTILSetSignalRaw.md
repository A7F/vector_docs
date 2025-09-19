[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILSetSignalRaw.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_SetSignalRaw**

# VTIL_SetSignalRaw

[Feature availability for your product](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_SetSignalRaw( dbSignal signal, long value );
long VTIL_SetSignalRaw( dbNode vt, dbSignal signal, long value ); // form 2
```

## Description

Sets the signal to the specified raw value. The message of the signal is sent according to the configured send type.

## Parameters

- **signal**: Signal name from database. The signal must be assigned to the node as Tx signal.
- **value**: raw value
- **vt**: VT simulation node to apply the function

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example for simulation node:

```plaintext
void SendLanguageCommand_English()
{
  VTIL_SetSignalRaw( LC_VT::LanguageCodeCmd, 0x6E65 );
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
