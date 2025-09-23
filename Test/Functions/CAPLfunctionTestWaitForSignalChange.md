# TestWaitForSignalChange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestWaitForSignalChange(Signal aSignal, dword aTimeout);
```

## Description

Waits for an event from a signal which value is changed.

## Parameters

- **aSignal**: Signal to be queried
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Signal is not valid
- **-1**: General error
- **0**: Wait state is exited due to a timeout
- **1**: Wait state is exited due to condition fulfillment

## Example

```c
// waits 1000ms for change of signal "Velocity"
long result;
result = TestWaitForSignalChange(Node_SUT::Velocity, 1000);
```
