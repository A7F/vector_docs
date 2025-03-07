[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILSetMsgEvent.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_SetMsgEvent**

# VTIL_SetMsgEvent

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_SetMsgEvent( dbMsg msg ); // form 1`
- `long VTIL_SetMsgEvent( dbNode vt, dbMsg msg ); // form 2`

## Description

The message is sent immediately, the send type is ignored. The VT IL must be in state **active** and the message must be assigned to the node as Tx message.

To modify signal values prior to message transmission, the CAPL functions [VTIL_SetSignal](CAPLfunctionIso11783VTILSetSignal.md) or [VTIL_SetSignalRaw](CAPLfunctionIso11783VTILSetSignalRaw.md) can be used.

## Parameters

- **msg**: Message name from database. The message must be a Tx message of the node.
- **vt**: VT simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example form 1**

```plaintext
on key 'i'
{
    VTIL_SetMsgEvent( ICC_VT );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)