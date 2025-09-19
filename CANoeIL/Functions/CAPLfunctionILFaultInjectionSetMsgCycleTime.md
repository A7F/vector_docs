# ILFaultInjectionSetMsgCycleTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILFaultInjectionSetMsgCycleTime (dbMsg msg, double value)
```

## Description

Assigns a new cycle time to the message. To set the cycle time back to its original value, use [ILFaultInjectionResetMsgCycleTime](CAPLfunctionILFaultInjectionResetMsgCycleTime.md).

## Parameters

- **msg**: Message that should get a new cycle time.
- **value**: New cycle time of the message in milliseconds.

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this function.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.

## Example

—

[ILFaultInjectionDisableMsg](CAPLfunctionILFaultInjectionDisableMsg.md) • [ILFaultInjectionEnableMsg](CAPLfunctionILFaultInjectionEnableMsg.md) • [ILFaultInjectionResetAllFaultInjections](CAPLfunctionILFaultInjectionResetAllFaultInjections.md)
