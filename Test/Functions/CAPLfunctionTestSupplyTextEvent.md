# TestSupplyTextEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TestSupplyTextEvent(char aText[]);
```

## Description

Signals the specified event.

Consequently resolves a possibly-active wait condition on this event.

If such a wait condition is active, the corresponding code will be executed immediately. The current function is therefore interrupted and the code will be executed at a later point in time after the `TestSupplyTextEvent` function call.

## Parameters

- **aText**: Name of the event to be signaled

## Return Values

- **0**: Event was signaled successfully
- **-1**: Event could not be signaled

## Example

```plaintext
// Signals the occurrence of an Error Frame as a text event
on errorFrame
{
    TestSupplyTextEvent("ErrorFrame occurred!")
}
```

[TestWaitForTextEvent](CAPLfunctionTestWaitForTextEvent.md) • [TestJoinTextEvent](CAPLfunctionTestJoinTextEvent.md)
