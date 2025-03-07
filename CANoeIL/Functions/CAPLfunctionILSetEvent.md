[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILSetEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILSetEvent

# ILSetEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
It is strongly recommended to use this functionality only for test purposes and not in real simulations. The database should be corrected instead.

## Function Syntax

```
long ILSetEvent (dbSignal sig)
```

## Description

Sends the transferred signal directly to the bus if the network is active. The send model is ignored.

## Parameters

- **sig**: Signal that should be sent. Specify as follows 'Message::Signal'.

## Return Values

- **0**: No error.
- **1**: Momentary state of the IL does not permit this query.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.
- **-100**: Signal or message was not found in the database or is not mapped to this node.
- **-104**: General error for invalid calls.

## Example

—

[ILSetMsgEvent](CAPLfunctionILSetMsgEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)