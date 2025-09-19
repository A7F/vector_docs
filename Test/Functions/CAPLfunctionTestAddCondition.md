[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestAddCondition.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestAddCondition

# TestAddCondition

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestAddCondition (dword aAuxHandle);`
- `long TestAddCondition (dword aAuxHandle, long aBehavior);`
- `long TestAddCondition (char aEventText[]);`
- `long TestAddCondition (char aEventText[], long aBehavior);`

## Description

Adds an event object or an event text as a condition. Checks from the Test Service Library are suitable as event objects. This function can be used within a test case and also on the main test level.

## Parameters

- **aAuxHandle**: Event object, e.g., a check from the TestService Library. Specified is the handle that is returned when a check is created.
- **aEventText**: Textual name of an event whose occurrence should be monitored. This event can be triggered with the function [TestSupplyTextEvent](CAPLfunctionTestSupplyTextEvent.md).
- **aBehavior**: Normally in case of a condition injury, only a corresponding entry is made in the test report and the verdict of the active test case is set to "fail". In exceptional cases, this behavior can be set otherwise:
  - **0**: Default behavior, entry in test report and setting of the verdict to "fail"
  - **1**: Only an entry in the test report is made, the verdict remains unchanged
  - **2, 3**: reserved

## Return Values

- **0**: Condition was added successfully
- **< 0**: Condition could not be added

## Example

**Example 1**

Add check as condition

```plaintext
dword checkId;
dword numCheckEvents;

// start the Error Frame observation
checkId = ChkStart_ErrorFramesOccured();
// Add check as condition,
// that means that check violations are reported and
// the verdict of the test case is set to "failed"
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
// Remove check as condition
TestRemoveCondition(checkId);

// stop the check
ChkControl_Stop(checkId);
// reset stored values of the check
ChkControl_Reset(checkId);

// start the check again without adding as condition,
// that means that Error Frames are observed, but violations
// are not reported and do not set the test case verdict to "failed"
ChkControl_Start(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
// stop the check
ChkControl_Stop(checkId);

// analysis of check
numCheckEvents = ChkQuery_NumEvents(checkId);
if (numCheckEvents > 0)
    TestStepFail("Error Frame occurred!");

// destroy check
ChkControl_Destroy(checkId);
```

**Example 2**

Add text event as condition

```plaintext
// test case to check if Error Frames occur
testcase CheckErrorFrameReceived ()
{
    TestAddCondition("ErrorFrameReceived");
    // sequence of different actions and waiting conditions
    TestWaitForTimeout(1000);
    TestRemoveCondition("ErrorFrameReceived");
}

// handler to supply text event
on errorFrame
{
    TestSupplyTextEvent("ErrorFrameReceived");
}
```

[TestRemoveCondition](CAPLfunctionTestRemoveCondition.md) • [TestCheckCondition](CAPLfunctionTestCheckCondition.md) • [TestSupplyTextEvent](CAPLfunctionTestSupplyTextEvent.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
