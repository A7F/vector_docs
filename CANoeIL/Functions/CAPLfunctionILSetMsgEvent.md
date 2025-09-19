# ILSetMsgEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
It is strongly recommended to use this functionality only for test purposes and not in real simulations. The database should be corrected instead.

## Function Syntax

`long ILSetMsgEvent (dbMsg msg)`

## Description

Sends the transferred message directly to the bus if the network is active. The send model is ignored.

## Parameters

- **msg**: Message that should be sent.

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this query.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.
- **-104**: General error for invalid calls.

## Example

—

[ILSetEvent](CAPLfunctionILSetEvent.md)
