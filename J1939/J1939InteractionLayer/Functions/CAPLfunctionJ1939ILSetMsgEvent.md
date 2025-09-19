[J1939ILSetMsgEvent](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILSetMsgEvent.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILSetMsgEvent

# J1939ILSetMsgEvent

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILSetMsgEvent( dbMsg msg ); // form 1
long J1939ILSetMsgEvent(dbNode node, dbMsg msg ); // form 2
```

## Description

The message is sent immediately, the send type is ignored. The J1939 IL must be in state [active](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILStates.md) and the message must be assigned to the node as Tx message.

To modify signal values prior to message transmission, the CAPL functions [J1939ILSetSignal](CAPLfunctionJ1939ILSetSignal.md) or [J1939ILSetSignalRaw](CAPLfunctionJ1939ILSetSignalRaw.md) can be used.

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
    J1939ILSetMsgEvent( EC1 );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
