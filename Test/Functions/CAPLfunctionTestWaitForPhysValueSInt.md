# TestWaitForPhysValueSInt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestWaitForPhysValueSInt(valueHandle * value, int64 awaitedValue, dword timeoutMs);
```

## Description

Waits for the **phys** encoding of a **valueHandle** to reach a certain value. This function can only be used for **valueHandles** with a signed integer data type. It cannot be used for system variables or bus system signals.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **awaitedValue**: Value which is awaited.
- **timeoutMS**: Timeout in milliseconds.

## Return Values

- **-2**: Resume due to constraint violation.
- **-1**: General error, for example, functionality is not available.
- **0**: Resume due to timeout.
- **1**: Resume due to event occurred (value has been reached).

## Example

```c
long ret;
ret = testWaitForPhysValueSInt(ErrorSignal[LeftMirror], -1, 200)
```

[TestWaitForPhysValueFloat](CAPLfunctionTestWaitForPhysValueFloat.md) • [TestWaitForPhysValueUInt](CAPLfunctionTestWaitForPhysValueUInt.md)
