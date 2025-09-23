# TestJoinAuxEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestJoinAuxEvent(dword aAuxEventId)
```

## Description

Completes the current set of "joined events" with the transmitted event. This function does not wait.

## Parameters

- **aAuxEventId**: Auxiliary event id that should be awaited

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **\> 0**: Number of the joined event

## Example

```c
// wait is resumed on check event
dword index = 0;
dword checkId = 0;
checkId = ChkStart_Timeout(1000);
TestJoinAuxEvent(checkId);
// … other join events
TestJoinEnvVarEvent(MyEnvVar);
TestJoinSignalInRange(Velocity, 80, 100);
TestJoinTextEvent("ErrorFrame occurred!");

index = TestWaitForAnyJoinedEvent(2000);
```

[TestWaitForAuxEvent](CAPLfunctionTestWaitForAuxEvent.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)
