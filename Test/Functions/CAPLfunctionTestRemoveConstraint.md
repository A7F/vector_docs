[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestRemoveConstraint.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestRemoveConstraint

# TestRemoveConstraint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note:** Conditions can only be removed in the test case or on the test module level on which they were also added. If a test case is abandoned, then the constraints created in this test case are removed automatically. Similarly, with the end of a test module, all constraints are removed automatically.

## Function Syntax

```plaintext
long TestRemoveConstraint (dword aAuxHandle);
long TestRemoveConstraint (char aEventText[]);
```

## Description

Removes an event object or an event text that was added as a constraint. This function can be used both within a test case and also on the test module level.

## Parameters

- **aAuxHandle**: Event object, for example a check from the TestService Library. Specified is the handle that is returned when a check is created.
- **aEventText**: Textual name of an event whose occurrence should be monitored. This event can be triggered with the function [TestSupplyTextEvent](CAPLfunctionTestSupplyTextEvent.md).

## Return Values

- **0**: Constraint was removed successfully
- **!= 0**: Constraint could not be removed

## Example

```plaintext
dword checkId;
dword numCheckEvents;

// start the Error Frame observation
checkId = ChkStart_ErrorFramesOccured();
// Add check as constraint,
// that means that check violations are reported and
// the verdict of the test case is set to "failed"
TestAddConstrait(checkId);
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

[TestAddConstraint](CAPLfunctionTestAddConstraint.md) • [TestCheckConstraint](CAPLfunctionTestCheckConstraint.md) • [TestSupplyTextEvent](CAPLfunctionTestSupplyTextEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)