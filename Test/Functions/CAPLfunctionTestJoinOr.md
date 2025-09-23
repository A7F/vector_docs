# TestJoinOr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinOr(long aEventHandle1, long aEventHandle2); // form 1`
- `long TestJoinOr(long aEventHandle1, long aEventHandle2, long aEventHandle3); // form 2`
- `long TestJoinOr(dword aNumHandles, long aEventHandles[]); // form 3`

## Description

Adds a logical OR-expression of two or more events that were previously joined to the current set of "joined events". Combined with [TestJoinAnd](CAPLfunctionTestJoinAnd.md), an arbitrary logical expression can be formed. This function does not wait.

## Parameters

- **aEventHandle1**, **aEventHandle2**, **aEventHandle3**: Event handle that was returned by a previous `TestJoin…`-function.
- **aNumHandles**: Number of elements in **aEventHandles**.
- **aEventHandles**: List of event handles. Each handle has to be the return value of a previous `TestJoin…`-function.

## Return Values

- **-3**: Join error
- **-2**: Invalid event handle(s)
- **-1**: General error, for example, functionality is not available
- **\> 0**: Number of the joined event

## Example

```plaintext
long handle1, handle2, result;

// condition 1
handle1 = TestJoinOr(TestJoinSignalInRange(Node_SUT::Velocity, 90, 100) TestJoinSignalInRange(Node_SUT::Velocity, 30, 40));

// condition 2
Handle2 = TestJoinOr(TestJoinSignalMatch(Node_SUT::HeadLightLeft, 1), TestJoinSignalMatch(Node_SUT::HeadLightRight, 1));

// waits until condition 1 and condition 2 is fulfilled
result = TestWaitForAllJoinedEvents(500);
```

[TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForJoinedEvent](CAPLfunctionTestWaitForJoinedEvent.md) • [TestJoinAnd](CAPLfunctionTestJoinAnd.md)
