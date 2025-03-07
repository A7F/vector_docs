[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILFaultInjectionDisableMsg.md)

**CAPL Functions** » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILFaultInjectionDisableMsg

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)