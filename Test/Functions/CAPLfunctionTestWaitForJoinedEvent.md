# TestWaitForJoinedEvent

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
Regardless of how the wait point was discontinued, afterwards the set of "joined events" is empty. That is, waiting for "joined events" always empties the previously defined set of "joined events".

## Function Syntax

- `long TestWaitForJoinedEvent(long aEventHandle, dword aTimeout); // form 1`
- `long TestWaitForJoinedEvent(long aEventHandle, bool aAndEventsAllAtLeastOnce, dword aTimeout); // form 2`
- `long TestWaitForJoinedEvent(long aEventHandle, bool aAndEventsAllAtLeastOnce, long aStopHandle, dword aTimeout); // form 3`

## Description

Waits for the specified joined event. The wait condition is resolved when the specified joined event is signaled. In the case of form 3, the wait condition is also resolved when the **aStopHandle** event is signaled.

If neither event occurs before the expiration of the specified time **aTimeout**, the wait condition is resolved nevertheless.

## Parameters

- **aEventHandle**: Event handle that was returned by a previous `TestJoin…`-function.
- **aAndEventsAllAtLeastOnce**: When set to 1, conditions within condition compositions formed with [TestJoinAnd](CAPLfunctionTestJoinAnd.md) only need to match at least once. If **aAndEventsAllAtLeastOnce** is not set (i.e., it is 0), form 1 and form 2 are identical.
- **aStopHandle**: Event handle that was returned by a previous `TestJoin…`-function. Allows for an additional stop criterion besides the timeout.
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **> 0**: Joined event or stop event occurred. The index of the final event is returned, indicating what has triggered the resolution.

## Example

```plaintext
long handle1, handle2, handle3, stopHandle, result;

// form 1
handle1 = TestJoinAnd(TestJoinSignalMatch(Node_SUT::Velocity, 80), TestJoinSignalMatch(Ignition::Switch, 1));
handle2 = TestJoinAnd(TestJoinSignalMatch(Node_SUT::Velocity, 0), TestJoinSignalMatch(Ignition::Switch, 0));
handle3 = TestJoinOr(handle1, handle2);
result = testWaitForJoinedEvent(handle3, 500);

// form 2
handle1 = TestJoinAnd(TestJoinSignalMatch(Node_SUT::Velocity, 80), TestJoinSignalMatch(Node_SUT::Velocity, 70), TestJoinSignalMatch(Node_SUT::Velocity, 60));
result = testWaitForJoinedEvent(handle1, 1, 500);
// If the timeout was not reached, Node_SUT::Velocity has been 60, 70 and 80 at least once during the wait time.

// form 3
stopHandle = TestJoinSignalMatch(Ignition::Switch, 0);
handle1= TestJoinOr(TestJoinSignalMatch(Node_SUT::Velocity, 80), TestJoinSignalMatch(Node_SUT::Velocity, 70));
result = testWaitForJoinedEvent(handle1, 0, stopHandle, 500);
```

[TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestJoinAnd](CAPLfunctionTestJoinAnd.md) • [TestJoinOr](CAPLfunctionTestJoinOr.md)
