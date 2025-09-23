# TestJoinUpdateFlag

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestJoinUpdateFlag(valueHandle * value);
```

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait.

## Parameters

- **value**: Value handle of a communication object or distributed object.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```plaintext
long ret;
consumedEventRef * anEvent;
anEvent = lookupConsumedEvent(path);

anEvent.ClearChangeFlag();
// ...
ret = testJoinUpdateFlag(anEvent);
index = TestWaitForAllJoinedEvents(2000);
```

[TestJoinUpdate](CAPLfunctionTestJoinUpdate.md) • [TestJoinUpdateCountGreater](CAPLfunctionTestJoinUpdateCountGreater.md) • [TestJoinChangeFlag](CAPLfunctionTestJoinChangeFlag.md)
