# TestJoinTextEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestJoinTextEvent(char[]aText)
```

## Description

Completes the current set of "joined events" with the transmitted event. This function does not wait.

## Parameters

- **aText**: Textual event that should be awaited

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```c
// waits for a specified text event
long result;
dword index = 0;
result = TestJoinTextEvent("ErrorFrame occurred!");
// ... other join events
TestJoinEnvVarEvent(MyEnvVar);
TestJoinSignalInRange(Velocity, 80, 100);

index = TestWaitForAnyJoinedEvent(2000);

// on ErrorFrame handler
on errorFrame
{
    TestSupplyTextEvent("ErrorFrame occurred!");
}
```

[TestWaitForTextEvent](CAPLfunctionTestWaitForTextEvent.md) • [TestSupplyTextEvent](CAPLfunctionTestSupplyTextEvent.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)
