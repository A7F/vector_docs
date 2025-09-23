# SomeIpILControlInit

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpILControlInit();
```

## Description

Initialization of SOME/IP IL.

Prevents the SOME/IP IL from starting automatically. If this function is used, the SOME/IP IL must then be started with the [SomeIpILControlStart](CAPLfunctionSomeIpILControlStart.md) function.

This function may only be used in `on preStart`.

## Parameters

—

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on preStart
{
  // prevent auto start
  SomeIpILControlInit();
}
```

[See Also](javascript:void(0);)
