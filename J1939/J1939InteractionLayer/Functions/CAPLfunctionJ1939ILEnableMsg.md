# J1939ILEnableMsg

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILEnableMsg(dbMsg dbMessage); // form 1
long J1939ILEnableMsg(dbNode node, dbMsg dbMessage); // form 2
```

## Description

Re-enables the sending of the message after having disabled it with [ILFaultInjectionDisableMsg](../../../CANoeIL/Functions/CAPLfunctionILFaultInjectionDisableMsg.md)/[J1939ILDisableMsg](CAPLfunctionJ1939ILDisableMsg.md).

## Parameters

- **dbMessage**: message name as defined in the database
- **node**: Simulation node to apply the function

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
