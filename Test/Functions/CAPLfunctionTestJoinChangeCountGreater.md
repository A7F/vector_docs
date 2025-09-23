# TestJoinChangeCountGreater

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestJoinChangeCountGreater(valueHandle * value, qword count);
```

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **count**: Change count to be reached.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **\> 0**: Number of the joined event

## Example

```c
long ret;
consumedEventRef * anEvent;
anEvent = lookupConsumedEvent(path);
// ...
ret = testJoinChangeCountGreater(anEvent, anEvent.GetChangeCount() + 3);
index = TestWaitForAllJoinedEvents(2000);
```

[TestJoinChange](CAPLfunctionTestJoinChange.md) • [TestJoinChangeFlag](CAPLfunctionTestJoinChangeFlag.md) • [TestJoinUpdateCountGreater](CAPLfunctionTestJoinUpdateCountGreater.md)
