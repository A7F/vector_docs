# TestWaitForAllJoinedEvents

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
Regardless of how the wait point was discontinued, afterwards the set of "joined events" is empty. That is, waiting for "joined events" always empties the previously defined set of "joined events".

## Function Syntax

```plaintext
long TestWaitForAllJoinedEvents(dword aTimeout); // form 1
long TestWaitForAllJoinedEvents(dword aAtLeastOnce, dword aTimeout); // form 2
```

## Description

Waits for the current set of "joined events." The wait condition is resolved if all of the joined events were signaled. With form 1 the conditions of "joined events" must match at the same time. With form 2 each condition must have occurred only at least once.

Note that this time behavior only impacts conditions whose state (fulfilled or unfulfilled) can change over time. For instance, [TestJoinSignalMatch](CAPLfunctionTestJoinSignalMatch.md) may be fulfilled at a certain point but could change if the corresponding signal value is modified again. In contrast, conditions like [TestJoinTextEvent](CAPLfunctionTestJoinTextEvent.md) will be fulfilled once the corresponding text event is signaled but will never become unfulfilled.

Should not all events occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

## Parameters

- **aAtLeastOnce**  
  If set the conditions of "joined events" do not have to match at the same time. Conditions must match only at least once before timeout.  
  If not set, i.e., aAtLeastOnce is 0, form 1 and form 2 are identical.

- **aTimeout**  
  Maximum time that should be waited [ms]  
  (Transmission of 0: no timeout controlling)

## Return Values

- **-2**  
  Resume due to constraint violation

- **-1**  
  General error, for example, functionality is not available

- **0**  
  Resume due to timeout

- **\> 0**  
  All joined events occurred. The index of the final event is returned, indicating what has triggered the resolution.

## Example

**Example Form 1**

```plaintext
// waits for all conditions to be fulfilled at the same time
TestJoinEnvVarEvent(MyEnvVar);
TestJoinSignalInRange(Velocity, 80, 100);
TestJoinTextEvent("ErrorFrame occurred!");
TestWaitForAllJoinedEvents(5000);
```

**Example Form 2**

```plaintext
// waits for all conditions to be fulfilled at least once
TestJoinEnvVarEvent(MyEnvVar);
TestJoinSignalInRange(Velocity, 80, 100);
TestJoinTextEvent("ErrorFrame occurred!");
TestWaitForAllJoinedEvents(1, 5000);
```

[TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestJoinMessageEvent](CAPLfunctionTestJoinMessageEvent.md) • [TestJoinAuxEvent](CAPLfunctionTestJoinAuxEvent.md) • [TestJoinTextEvent](CAPLfunctionTestJoinTextEvent.md) • [TestJoinSignalInRange](CAPLfunctionTestJoinSignalInRange.md) • [TestJoinSignalOutsideRange](CAPLfunctionTestJoinSignalOutsideRange.md) • [TestJoinSignalMatch](CAPLfunctionTestJoinSignalMatch.md)
