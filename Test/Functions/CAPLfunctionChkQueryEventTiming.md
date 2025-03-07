[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryEventTiming.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_EventTiming

# ChkQuery_EventTiming

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
float ChkQuery_EventTiming (dword checkId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.QueryEventTiming();
```

## Description

Retrieves the timing value that has been violated in the LIN specific check.

## Parameters

- **checkId**: Identifier of the queried Check.

## Return Values

- **< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **≥ 0**: Timing value depending on the check type

## Available For

- [ChkStart_LINSyncBreakTimingViolation](CAPLfunctionChkStartLinSyncBreakTimingViolation.md): Result: Last measured break length [in bit times]
- [ChkStart_LINSyncDelTimingViolation](CAPLfunctionChkStartLinSyncDelTimingViolation.md): Result: Last measured delimiter length [in bit times]
- [ChkStart_LINMasterBaudrateViolation](CAPLfunctionChkStartLinMasterBaudrateViolation.md): Result: Last measured baudrate [in bit times]

## Example

```plaintext
testcase tcTSL_LINSyncBreak()
{
   dword checkId;
   float lastMeasuredSyncBreakLength;

   checkId = ChkStart_LINSyncBreakTimingViolation (18, 20);
   testWaitForTimeout(5000);
   ChkControl_Stop(checkId);

   lastMeasuredSyncBreakLength = ChkQuery_EventTiming(checkId);
   testStep("Evaluation", "Last measured sync break length is %.2f bits", lastMeasuredSyncBreakLength);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)