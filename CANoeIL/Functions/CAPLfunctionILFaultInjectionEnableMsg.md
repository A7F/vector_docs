# ILFaultInjectionEnableMsg

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILFaultInjectionEnableMsg (dbMsg msg)
```

## Description

Enables the sending of the message.

## Parameters

- **msg**: Message that should be re-enabled after having disabled it with [ILFaultInjectionDisableMsg](CAPLfunctionILFaultInjectionDisableMsg.md).

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this function.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.

## Example

—

[ILFaultInjectionResetAllFaultInjections](CAPLfunctionILFaultInjectionResetAllFaultInjections.md) • [ILFaultInjectionResetMsgCycleTime](CAPLfunctionILFaultInjectionResetMsgCycleTime.md) • [ILFaultInjectionSetMsgCycleTime](CAPLfunctionILFaultInjectionSetMsgCycleTime.md)
