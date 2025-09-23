# TestJoinPhysValueFloat

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestJoinPhysValueFloat(valueHandle * value, float awaitedValue); // form 1`
- `long TestJoinPhysValueFloat(valueHandle * value, float awaitedValue, dword waitForValueUpdate); // form 2`

## Description

Completes the current set of **joined events** with the transmitted event. This function can only be used for **valueHandles** with a floating point data type. This function does not wait.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **awaitedValue**: Value which is awaited.
- **waitForSignalUpdate**: Condition should be checked immediately when the set of joined events is evaluated by [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) or [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md), or condition should be checked when the next message with the given signal will arrive.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **\> 0**: Number of the joined event

## Example

```plaintext
long ret;
dword index = 0;
ret = testJoinPhysValueFloat(MirrorStatus[CANoe].Temperature, 20.0, 1);

index = TestWaitForAnyJoinedEvent(2000);
```

[TestJoinPhysValueSInt](CAPLfunctionTestJoinPhysValueSInt.md) • [TestJoinPhysValueUInt](CAPLfunctionTestJoinPhysValueUInt.md)
