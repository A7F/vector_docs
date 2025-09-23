# TestWaitForAnyJoinedEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
Regardless of how the wait point was discontinued, afterwards the set of "joined events" is empty. That is, waiting for "joined events" always empties the previously defined set of "joined events".

## Function Syntax

```
long TestWaitForAnyJoinedEvent(dword aTimeout);
```

## Description

Waits for the current set of "joined events." Each individual of these events can resolve the wait state.

Should none of the events occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

## Parameters

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
- **> 0**  
  Resume due to event occurred The return value returns the number of the joined event that triggered the resolution.

## Example

```plaintext
variables
{
  long EventHandle1, EventHandle2, lReturn;
  int64 mEventTime;
  long Res;
}

MainTest()
{
  _WaitForAnyEvent();
}

on errorFrame
{
  Res = TestSupplyTextEvent("ErrorFrame occurred!");
}

testcase _WaitForAnyEvent()
{
  TestCaseTitle("Demo","WaitForAnyJoinedEvents");

  EventHandle1 = testJoinSysVarEvent(sysvar::Sysvar1);
  EventHandle2 = TestJoinTextEvent("ErrorFrame occurred!");

  lReturn = TestWaitForAnyJoinedEvent (5000);

  if (lReturn > 0)
  {
    if (lReturn == EventHandle1)
    {
      Res = testGetJoinedEventOccured(lReturn, mEventTime);
      write("mEventTime = %I64d ; Res = %ld ; lReturn = %ld",mEventTime,Res,lReturn);
    }
    if (lReturn == EventHandle2)
    {
      Res = testGetJoinedEventOccured(lReturn, mEventTime);
      write("mEventTime = %I64d ; Res = %ld ; lReturn = %ld",mEventTime,Res,lReturn);
    }
  }
}
```

[TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestJoinMessageEvent](CAPLfunctionTestJoinMessageEvent.md) • [TestJoinAuxEvent](CAPLfunctionTestJoinAuxEvent.md) • [TestJoinTextEvent](CAPLfunctionTestJoinTextEvent.md) • [TestJoinSignalInRange](CAPLfunctionTestJoinSignalInRange.md) • [TestJoinSignalOutsideRange](CAPLfunctionTestJoinSignalOutsideRange.md) • [TestJoinSignalMatch](CAPLfunctionTestJoinSignalMatch.md)
