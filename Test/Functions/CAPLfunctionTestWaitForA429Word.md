[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForA429Word.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForA429Word**

# TestWaitForA429Word

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestWaitForA429Word (dbA429Word aWord, dword aTimeout);`
- `long TestWaitForA429Word (dword aLabel, dword aTimeout);`
- `long TestWaitForA429Word (dword aTimeOut);`

## Description

Wait for the occurrence of the specified word `aWord`. If the ARINC word does not occur before the expiration of the time `aTimeout`, the wait condition is resolved nevertheless. If no specific ARINC word is given, the wait condition is resolved on any word.

If ARINC word events are delivered from different buses, the context has to be adjusted correctly ([SetBusContext](../../Other/Functions/CAPLfunctionSetBusContext.md)).

The function handles only incoming and error-free ARINC words.

## Parameters

- **aWord**: Event connected to ARINC word from an assigned database.
- **aLabel**: Event connected to ARINC label [1 .. 255].
- **aTimeout**: Maximum time that should be waited [ms]; Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error (e.g., functionality not available)
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```c
// Example
// This example waits for the occurrence of two messages in correct order
variables
{
  dword a429Ch5Context = 0;
  dword a429Ch6Context = 0;
  long resultTestWait = 0;

  dword timeToWait = 5000; // in ms
}

MainTest()
{
  // save the bus context for later use
  a429Ch5Context = getBusNameContext("A429Ch5");
  a429Ch6Context = getBusNameContext("A429Ch6");

  TestWaitForA429Word_Two();
}

testcase TestWaitForA429Word_Two()
{
  a429word * myWord;
  dword index = 0;

  TestStepPass("Library: Test.can", "Testcase: TestWaitForA429Word_Two");

  TestStep("Wait Condition", "Create Wait for LBL_075");
  
  setBusContext(a429Ch5Context);
  CheckWaitResult(testWaitForA429Word(LBL_075, timeToWait));

  TestStep("Wait Condition", "Create Wait for LBL_012");
  setBusContext(a429Ch6Context);
  CheckWaitResult(testWaitForA429Word(LBL_012, timeToWait));
}

testfunction CheckWaitResult(long result)
{
  if (result < 0)
  {
    TestStepFail("Wait Condition", "result = %d, Failure on joining symbolic event: LBL_075", result);
  }
  else if (result == 0)
  {
    TestStepFail("Wait Condition", "result = %d, Failure on waiting symbolic event: LBL_075, event did not occur", result);
  }
  else
  {
    TestStepPass("Wait Condition", "Awaited symbolic event occurred");
  }
}
```

[TestJoinA429WordEvent](CAPLfunctionTestJoinA429WordEvent.md) • [TestGetWaitEventMsgData](CAPLfunctionTestGetWaitEventMsgData.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
