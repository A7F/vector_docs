[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetJoinedEventOccured.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » testGetJoinedEventOccured

# testGetJoinedEventOccured

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long testGetJoinedEventOccured(dword index, int64& occurrenceTime);
```

## Description

Retrieves the occurrence and the occurrence time of a joined event.

## Parameters

- **index**: Number of the "joined event" corresponds with the return value of **testJoin...**.
- **occurrenceTime**: The variable will be filled with the time when the event occurred.

## Return Values

- **0**: Event not occurred
- **1**: Event occurred

## Example

```plaintext
MainTest()
{
  WaitForAllEvents();
}

on errorFrame
{
  TestSupplyTextEvent("ErrorFrame occurred!");
}

testcase WaitForAllEvents()
{
  const dword waitDuration = 5000; // [ms]
  long  eventHandle1, eventHandle2;
  int64 eventTime1  , eventTime2  ;
  long  res;

  TestCaseTitle("Demo", "WaitForAllEvents");

  eventHandle1 = testJoinSysVarEvent(sysvar::Sysvar1);
  eventHandle2 = TestJoinTextEvent("ErrorFrame occurred!");
  res = TestWaitForAllJoinedEvents(waitDuration);

  if (res > 0) // all events occurred, last one is stored in res
  {
    write("All expected events occurred");
  }
  else
  {
    write("Timeout after %d ms: Not all expected events occurred", waitDuration);
  }

  if (testGetJoinedEventOccured(eventHandle1, eventTime1) == 1)
  {
    write("SysVar1 changed at %I64d", eventTime1);
  }
  else
  {
    write("SysVar1 unchanged");
  }

  if (testGetJoinedEventOccured(eventHandle2, eventTime2) == 1)
  {
    write("Errorframe occurred at %I64d", eventTime2);
  }
  else
  {
    write("No Errorframe");
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
