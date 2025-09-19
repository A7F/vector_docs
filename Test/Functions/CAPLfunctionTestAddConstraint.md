[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestAddConstraint.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestAddConstraint

# TestAddConstraint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestAddConstraint (dword aAuxHandle);`
- `long TestAddConstraint (dword aAuxHandle, long aBehavior);`
- `long TestAddConstraint (char aEventText[]);`
- `long TestAddConstraint (char aEventText[], long aBehavior);`

## Description

Adds an event object or an event text as a constraint. Checks from the Test Service Library are suitable as event objects. This function can be used within a test case and also on the main test level.

## Parameters

- **aAuxHandle**: Event object, for example a check from the TestService Library. Specified is the handle that is returned when a check is created.
- **aEventText**: Textual name of an event whose occurrence should be monitored. This event can be triggered with the function [TestSupplyTextEvent](CAPLfunctionTestSupplyTextEvent.md).
- **aBehavior**: Normally in case of a constraint injury, only a corresponding entry is made in the test report and the verdict of the active test case is set to "fail". In exceptional cases, this behavior can be set otherwise:
  - **0**: Default behavior, entry in test report and setting of the verdict to "fail"
  - **1**: Only an entry in the test report is made, the verdict remains unchanged
  - **2, 3**: reserved
  - **4**: In addition to the entry in the test report and the setting of the verdict to "fail," the current waiting point is also aborted. This behavior was introduced for reasons of compatibility with Version 5.0 and should only be selected in exceptional cases since here after each waiting point a corresponding query must be inserted.

## Return Values

- **0**: Constraint was added successfully
- **< 0**: Constraint could not be added

## Example

**Example 1**

Add check as constraint

```plaintext
dword checkId;
dword numCheckEvents;

// start the Error Frame observation
checkId = ChkStart_ErrorFramesOccured();
// Add check as constraint,
// that means that check violations are reported and
// the verdict of the test case is set to "failed"
TestAddConstraint(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
// Remove check as constraint
TestRemoveConstraint(checkId);

// stop the check
ChkControl_Stop(checkId);
// reset stored values of the check
ChkControl_Reset(checkId);

// start the check again without adding as constraint,
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

Add check as constraint

```plaintext
// test case to check if Error Frames occur
testcase CheckErrorFrameReceived ()
{
    TestAddConstraint("ErrorFrameReceived");
    // sequence of different actions and waiting conditions
    TestWaitForTimeout(1000);
    TestRemoveConstraint("ErrorFrameReceived");
}

// handler to supply text event
on errorFrame
{
    TestSupplyTextEvent("ErrorFrameReceived");
}
```

[TestRemoveConstraint](CAPLfunctionTestRemoveConstraint.md) • [TestCheckConstraint](CAPLfunctionTestCheckConstraint.md) • [TestSupplyTextEvent](CAPLfunctionTestSupplyTextEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
