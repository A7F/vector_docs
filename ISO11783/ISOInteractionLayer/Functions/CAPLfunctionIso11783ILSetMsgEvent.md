[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILSetMsgEvent.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_SetMsgEvent

# Iso11783IL_SetMsgEvent

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_SetMsgEvent( dbMsg msg );
```

## Description

The message is sent immediately, the send type is ignored. The ISO11783 IL must be in state **active** and the message must be assigned to the node as Tx message.

To modify signal values prior to message transmission, the CAPL functions [Iso11783IL_SetSignal](CAPLfunctionIso11783ILSetSignal.md) or [Iso11783IL_SetSignalRaw](CAPLfunctionIso11783ILSetSignalRaw.md) can be used.

## Parameters

- **msg**: message name from database
  - The message must be a Tx message of the node.

## Return Values

- **0**: success
- **< 0**: [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 't'
{
    Iso11783IL_SetMsgEvent( EC1 );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
