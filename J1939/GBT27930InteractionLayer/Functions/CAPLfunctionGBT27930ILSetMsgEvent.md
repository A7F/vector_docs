[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILSetMsgEvent.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_SetMsgEvent**

# GBT27930IL_SetMsgEvent

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_SetMsgEvent( dbMsg msg ); // form 1
long GBT27930IL_SetMsgEvent(dbNode node, dbMsg msg ); // form 2
```

## Description

The message is sent immediately, the send type is ignored. The GBT27930 IL must be in state [active](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILStates.md) and the message must be assigned to the node as Tx message.

To modify signal values prior to message transmission, the CAPL functions [GBT27930IL_SetSignal](CAPLfunctionGBT27930ILSetSignal.md) or [GBT27930IL_SetSignalRaw](CAPLfunctionGBT27930ILSetSignalRaw.md) can be used.

## Parameters

- **msg**: message name from database. The message must be a [Tx message](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILConfigureDB.md) of the node.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 't'
{
    GBT27930IL_SetMsgEvent( EC1 );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
