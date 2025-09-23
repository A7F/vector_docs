# J1939ILGetAddress

[Valid for: CANoe DE • CANoe4SW DE](../../../../Shared/FeatureAvailability.md)

## Function Syntax

- `long J1939ILGetAddress(); // form 1`
- `long J1939ILGetAddress(dbNode node); // form 2`

## Description

Returns the address that is used by the J1939 IL.

## Parameters

- **node**: Simulation node to apply the function

## Return Values

- **≥ 0**: address of the J1939 IL
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```c
on key 'a'
{
  LONG addr;
  addr = J1939ILGetAddress();
}
```
