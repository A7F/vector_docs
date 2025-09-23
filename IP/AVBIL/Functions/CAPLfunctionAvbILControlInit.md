# AvbILControlInit

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AvbILControlInit();
```

## Description

Initialization of the AVB IL.

Initializes, but prevents the AVB IL, i.e. the simulated time aware end station (PTP clock instance), from starting automatically. If this function is used, the AVB IL must then be started with the [AvbILControlStart](CAPLfunctionAvbILControlStart.md) function.

This function may only be used in `on preStart`.

## Parameters

—

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

[See Also](javascript:void(0);)
