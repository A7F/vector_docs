# J1939ILDisableMsg

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILDisableMsg(dbMsg dbMessage); // form 1
long J1939ILDisableMsg(dbNode node, dbMsg dbMessage); // form 2
```

## Description

Disables the sending of the message except by calling the function [J1939ILSetMsgEvent](CAPLfunctionJ1939ILSetMsgEvent.md).

## Parameters

- **dbMessage**: message name as defined in the database
- **node**: Simulation node to apply the function

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
