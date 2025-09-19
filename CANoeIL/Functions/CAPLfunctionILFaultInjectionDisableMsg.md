# ILFaultInjectionDisableMsg

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILFaultInjectionDisableMsg (dbMsg msg)
```

## Description

Disables the sending of the message except by calling the function [ILSetMsgEvent](CAPLfunctionILSetEvent.md).

## Parameters

- **msg**: Message that should be disabled.

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this function.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.

## Example

—

[ILFaultInjectionEnableMsg](CAPLfunctionILFaultInjectionEnableMsg.md) • [ILFaultInjectionResetAllFaultInjections](CAPLfunctionILFaultInjectionResetAllFaultInjections.md) • [ILFaultInjectionResetMsgCycleTime](CAPLfunctionILFaultInjectionResetMsgCycleTime.md) • [ILFaultInjectionSetMsgCycleTime](CAPLfunctionILFaultInjectionSetMsgCycleTime.md)
