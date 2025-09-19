# ILFaultInjectionSetMsgLength

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```
ILFaultInjectionSetMsgLength(dbMsg msg, dword msgLength)
```

## Description

Assigns a new message length (in bytes) to the message. To set the message length back to its original value, use [ILFaultInjectionResetMsgLength](CAPLfunctionILFaultInjectionResetMsgLength.md).

## Parameters

- **msg**: Message that should get a new message length.
- **msgLength**: New message length (in bytes) of the message.

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this function.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.

## Example

—
