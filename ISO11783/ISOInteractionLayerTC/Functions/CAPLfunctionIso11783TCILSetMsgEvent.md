[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILSetMsgEvent.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_SetMsgEvent

# TCIL_SetMsgEvent

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_SetMsgEvent( dbMsg msg ); // form 1`
- `long TCIL_SetMsgEvent( dbNode tc, dbMsg msg ); // form 2`

## Description

The message is sent immediately, the send type is ignored. The TC IL must be in state **active** and the message must be assigned to the node as Tx message.

To modify signal values prior to message transmission, the CAPL functions [TCIL_SetSignal](CAPLfunctionIso11783TCILSetSignal.md) or [TCIL_SetSignalRaw](CAPLfunctionIso11783TCILSetSignalRaw.md) can be used.

## Parameters

- **msg**: Message name from database. The message must be a Tx message of the node.
- **tc**: TC simulation node to apply the function.

## Return Values

—

## Example

```plaintext
on key 'i'
{
    TCIL_SetMsgEvent( ICC_TC );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)