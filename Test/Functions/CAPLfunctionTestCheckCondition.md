[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestCheckCondition.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestCheckCondition

# TestCheckCondition

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestCheckCondition (dword aAuxHandle);
long TestCheckCondition (char aEventText[]);
```

## Description

Checks whether the specified condition was already injured. This function can be used both within a test case and also on test module level.

## Parameters

- **aAuxHandle**: Event object, for example a check from the TestService Library. Specified is the handle that is returned on creation of a check. This function can be used both within a test case and also on the test module level.

- **aEventText**: Textual name of an event whose occurrence should be monitored. This event can be triggered with the function [TestSupplyTextEvent](CAPLfunctionTestSupplyTextEvent.md).

## Return Values

- **1**: Condition was already injured at least once
- **0**: Condition was not yet injured
- **< 0**: The function cannot be executed because, for example, the specified condition does not exist

## Example

**Example 1**

Add check as condition

```c
// checks the maximum duration of a sequence of actions
checkId = ChkStart_Timeout (1000);
TestAddCondition(checkId);
TestWaitForTimeout(1500);
result = TestCheckCondition(checkId);
if (result == 1)
    TestStepFail("Timeout already occurred after 1500 ms.");
// sequence of different actions and waiting conditions
TestRemoveCondition(checkId);
```

**Example 2**

Add text event as condition

```c
// test case to check if Error Frames occur
testcase CheckErrorFrameReceived ()
{
    TestAddCondition("ErrorFrameReceived");
    TestWaitForTimeout(1000);
    result = TestCheckCondition("ErrorFrameReceived");
    if (result == 1)
        TestStepFail("Error Frame already occurred after 1000 ms.");
    // sequence of different actions and waiting conditions
    TestRemoveCondition("ErrorFrameReceived");
}
// handler to supply text event
on errorFrame
{
    TestSupplyTextEvent("ErrorFrameReceived");
}
```

[TestAddCondition](CAPLfunctionTestAddCondition.md) • [TestSupplyEvent](CAPLfunctionTestSupplyTextEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
