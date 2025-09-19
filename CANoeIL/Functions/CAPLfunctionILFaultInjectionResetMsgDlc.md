# ILFaultInjectionResetMsgDlc

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`long ILFaultInjectionResetMsgDlc (dbMsg msg)`

## Description

Resets the DLC of the message to the database DLC, after having manipulated the DLC with [ILFaultInjectionSetMsgDlc](CAPLfunctionILFaultInjectionSetMsgDlc.md).

## Parameters

- **msg**: Message that should get the database DLC.

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this function.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.

## Example

—
