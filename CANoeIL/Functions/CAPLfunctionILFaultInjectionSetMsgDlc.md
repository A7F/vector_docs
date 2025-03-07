[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILFaultInjectionSetMsgDlc.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILFaultInjectionSetMsgDlc

# ILFaultInjectionSetMsgDlc

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILFaultInjectionSetMsgDlc (dbMsg msg, dword dlc)
```

## Description

Assigns a new DLC to the message. To set the DLC back to its original value, use [ILFaultInjectionResetMsgDlc](CAPLfunctionILFaultInjectionResetMsgDlc.md).

## Parameters

- **msg**: Message that should get a new DLC.
- **dlc**: New DLC of the message.

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this function.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)