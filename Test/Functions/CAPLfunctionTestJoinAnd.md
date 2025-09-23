# TestJoinAnd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinAnd(long aEventHandle1, long aEventHandle2); // form 1`
- `long TestJoinAnd(long aEventHandle1, long aEventHandle2, long aEventHandle3); // form 2`
- `long TestJoinAnd(dword aNumHandles, long aEventHandles[]); // form 3`

## Description

Adds a logical AND-expression of two or more events that were previously joined to the current set of "joined events". Combined with [TestJoinOr](CAPLfunctionTestJoinOr.md), an arbitrary logical expression can be formed. This function does not wait.

## Parameters

- **aEventHandle1**, **aEventHandle2**, **aEventHandle3**: Event handle that was returned by a previous `TestJoin…`-function.
- **aNumHandles**: Number of elements in **aEventHandle**.
- **aEventHandles**: List of event handles. Each handle has to be the return value of a previous `TestJoin…`-function.

## Return Values

- **-3**: Join error
- **-2**: Invalid event handle(s)
- **-1**: General error, for example, functionality is not available
- **\> 0**: Number of the joined event

## Example

```c
long handle1, handle2, result;

// condition 1
handle1= TestJoinAnd(TestJoinSignalMatch(Node_SUT::Velocity, 80), TestJoinSignalMatch(Ignition::Switch, 1));

// condition 2
Handle2= TestJoinAnd(TestJoinSignalMatch(Node_SUT::Velocity, 0), TestJoinSignalMatch(Ignition::Switch, 0));

// waits until either condition 1 or condition 2 is fullfilled
result = TestWaitForAnyJoinedEvent(500);
```

[TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForJoinedEvent](CAPLfunctionTestWaitForJoinedEvent.md) • [TestJoinOr](CAPLfunctionTestJoinOr.md)
