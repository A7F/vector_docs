# ILFaultInjectionResetAllFaultInjections

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILFaultInjectionResetAllFaultInjections()
```

## Description

Resets the fault injection settings for all messages of the node.

## Parameters

—

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this function.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.

## Example

—

[ILFaultInjectionDisableMsg](CAPLfunctionILFaultInjectionDisableMsg.md) • [ILFaultInjectionEnableMsg](CAPLfunctionILFaultInjectionEnableMsg.md) • [ILFaultInjectionResetMsgCycleTime](CAPLfunctionILFaultInjectionResetMsgCycleTime.md) • [ILFaultInjectionSetMsgCycleTime](CAPLfunctionILFaultInjectionSetMsgCycleTime.md)
