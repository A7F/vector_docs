# ILEnableMsg

**Valid for**: CANoe DE • CANoe4SW DE

## Note

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL.

## Function Syntax

```
long ILEnableMsg (char msgName[])
```

## Description

Enables the sending of the message.

## Parameters

- **msgName**: Message that should be re-enabled after having disabled it with [ILFaultInjectionDisableMsg](CAPLfunctionILFaultInjectionDisableMsg.md) / [ILDisableMsg](CAPLfunctionILDisableMsg.md).

## Return Values

- **0**: No error
- **-1**: Momentary state of the IL does not permit this function.

## Example

—

[ILFaultInjectionDisableMsg](CAPLfunctionILFaultInjectionDisableMsg.md) • [ILDisableMsg](CAPLfunctionILDisableMsg.md)
