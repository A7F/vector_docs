# J1939ILControlInit

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILControlInit(); // form 1
long J1939ILControlInit(dbNode node);  // form 2
```

## Description

This function can only be used in **on preStart**, to suppress the auto-start function of the IL.

## Parameters

- **node**: Simulation node to apply the function

## Return Values

0 on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on preStart
{
    J1939ILControlInit();
}
```
