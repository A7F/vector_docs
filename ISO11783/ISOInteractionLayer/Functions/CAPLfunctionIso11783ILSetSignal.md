[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILSetSignal.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_SetSignal**

# Iso11783IL_SetSignal

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_SetSignal( dbSignal signal, double value );
```

## Description

Sets the signal to the specified physical value. The message of the signal is sent according to the configured send type.

## Parameters

- **signal**: signal name from database  
  The signal must be assigned to the node as Tx signal.
- **value**: physical value

## Return Values

- **0**: success
- **< 0**: [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 't'
{
    Iso11783IL_SetSignal( EEC1::EngSpeed, 1200.0 );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)