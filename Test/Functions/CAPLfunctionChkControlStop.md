[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkControlStop.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md) » ChkControl_Stop

# ChkControl_Stop

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long ChkControl_Stop(dword aCheckId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.Stop();
```

## Description

Turns off the checking of the event condition.

## Parameters

- **aCheckId**: Must exist

## Return Values

- **0**: successful
- **< 0**: error

## Possible Errors

- Check for given id does not exist

## Example

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
