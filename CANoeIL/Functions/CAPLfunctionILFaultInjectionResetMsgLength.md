[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILFaultInjectionResetMsgLength.md)

**CAPL Functions** » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILFaultInjectionResetMsgLength

# ILFaultInjectionResetMsgLength

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILFaultInjectionResetMsgLength (dbMsg msg)
```

## Description

Resets the message length (in bytes) of the message to the database, after having manipulated the message length with [ILFaultInjectionSetMsgLength](CAPLfunctionILFaultInjectionSetMsgLength.md).

## Parameters

- **msg**: Message that should get the database message length.

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this function.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)