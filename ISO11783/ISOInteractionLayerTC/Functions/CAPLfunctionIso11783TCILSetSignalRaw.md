[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILSetSignalRaw.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_SetSignalRaw**

# TCIL_SetSignalRaw

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_SetSignalRaw( dbSignal signal, long value ); // form 1
long TCIL_SetSignalRaw( dbNode tc, dbSignal signal, long value ); // form 2
```

## Description

Sets the signal to the specified raw value. The message of the signal is sent according to the configured send type.

## Parameters

- **signal**: Signal name from database. The signal must be assigned to the node as Tx signal.
- **value**: raw value
- **tc**: TC simulation node to apply the function

## Return Values

—

## Example

```c
void SendLanguageCommand_English()
{
  TCIL_SetSignalRaw( LC_TC::LanguageCodeCmd, 0x6E65 );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)