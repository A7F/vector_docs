# ILFaultInjectionResetMsgCycleTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILFaultInjectionResetMsgCycleTime(dbMsg msg)
```

## Description

Resets the cycle time of the message to the database cycle time, after having manipulated the cycle time with [ILFaultInjectionSetMsgCycleTime](CAPLfunctionILFaultInjectionSetMsgCycleTime.md).

## Parameters

- **msg**: Message that should get the database cycle time.

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this function.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.

## Example

—

[ILFaultInjectionDisableMsg](CAPLfunctionILFaultInjectionDisableMsg.md) • [ILFaultInjectionEnableMsg](CAPLfunctionILFaultInjectionEnableMsg.md) • [ILFaultInjectionResetAllFaultInjections](CAPLfunctionILFaultInjectionResetAllFaultInjections.md)
