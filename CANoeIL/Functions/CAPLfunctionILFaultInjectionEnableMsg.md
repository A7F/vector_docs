[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILFaultInjectionEnableMsg.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILFaultInjectionEnableMsg

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)