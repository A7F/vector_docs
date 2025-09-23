# TestGetLastWaitResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestGetLastWaitResult();
```

## Description

Makes available the last occurred return value of a TestWait instruction once again.

## Parameters

—

## Return Values

See TestWait instructions

## Example

```c
TestWaitForTimeout(100);
Write("Waiting Result = %d", TestGetLastWaitResult());
```

[TestWaitForMessage](CAPLfunctionTestWaitForMessage.md) • [TestWaitForAuxEvent](CAPLfunctionTestWaitForAuxEvent.md) • [TestWaitForTextEvent](CAPLfunctionTestWaitForTextEvent.md) • [TestWaitForTimeout](CAPLfunctionTestWaitForTimeout.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)
