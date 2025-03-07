[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILFaultInjectionResetMsgDlc.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILFaultInjectionResetMsgDlc

# ILFaultInjectionResetMsgDlc

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`long ILFaultInjectionResetMsgDlc (dbMsg msg)`

## Description

Resets the DLC of the message to the database DLC, after having manipulated the DLC with [ILFaultInjectionSetMsgDlc](CAPLfunctionILFaultInjectionSetMsgDlc.md).

## Parameters

- **msg**: Message that should get the database DLC.

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this function.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)