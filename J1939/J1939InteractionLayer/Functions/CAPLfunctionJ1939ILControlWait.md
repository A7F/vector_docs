# J1939ILControlWait

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILControlWait(); // form 1`
- `long J1939ILControlWait(dbNode node); // form 2`

## Description

Sending messages is suspended. Setting of signal is not possible. Call [J1939ILControlResume](CAPLfunctionJ1939ILControlResume.md) to activate sending again.

## Parameters

- **node**: Simulation node to apply the function

## Return Values

0 on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 'w'
{
    J1939ILControlWait();
}
```
