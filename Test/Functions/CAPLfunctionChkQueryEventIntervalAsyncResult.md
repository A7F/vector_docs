[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryEventIntervalAsyncResult.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_EventInterval_AsyncResult

# ChkQuery_EventInterval_AsyncResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ChkQuery_EventInterval_AsyncResult(dword CheckId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
check.QueryEventIntervalAsyncResult();
```

## Description

Returns the last time-interval that has led to the event. The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **CheckId**: Handle of the check to be queried.

## Return Values

- **< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **≥ 0**: Refers to the frame id

## Available For

- [ChkCreate_MsgDistViolation](CAPLfunctionChkCreateMsgDistViolation.md): Result: last bad message distance
- [ChkCreate_MsgRelCycleTimeViolation](CAPLfunctionChkCreateMsgRelCycleTimeViolation.md): Result: last bad cycle time
- [ChkCreate_MsgRelOccurrenceViolation](CAPLfunctionChkCreateMsgRelOccurrenceViolation.md): Result: the last message with a bad cycle time
- [ChkCreate_NodeMsgsRelCycleTimeViolation](CAPLfunctionChkCreateNodeMsgsRelCycleTimeViolation.md): Result: last bad cycle time
- [ChkCreate_NodeMsgsRelOccurrenceViolation](CAPLfunctionChkCreateNodeMsgsRelOccurrenceViolation.md): Result: the last message with a bad cycle time
- [ChkStart_SignalCycleTimeViolation](CAPLfunctionChkStartSignalCycleTimeViolation.md): Result: last invalid cycle time
- [ChkStart_LINSchedTableViolation](CAPLfunctionChkStartLinSchedTableViolation.md): Result: Last measured slot delay time
- [ChkStart_LINSyncBreakTimingViolation](CAPLfunctionChkStartLinSyncBreakTimingViolation.md): Result: Retrieves the value of the last measured length of the break low phase
- [ChkStart_LINSyncDelTimingViolation](CAPLfunctionChkStartLinSyncDelTimingViolation.md): Result: Retrieves the value of the last measured length of the break delimiter
- [ChkStart_LINDiagDelayTimesViolation](CAPLfunctionChkStartLinDiagDelayTimesViolation.md): Result: Retrieves last measured P2_min or ST_min time
- [ChkStart_LINHeaderToleranceViolation](CAPLfunctionChkStartLinHeaderToleranceViolation.md): Result: Last measured header transmission time
- [ChkStart_LINRespToleranceViolation](CAPLfunctionChkStartLinRespToleranceViolation.md): Result: Last measured response transmission time
- [ChkStart_LINMasterInitTimeViolation](CAPLfunctionChkStartLinMasterInitTimeViolation.md): Result: Last measured Master initialization time
- [ChkStart_LINWakeupReqLengthViolation](CAPLfunctionChkStartLinWakeupReqLengthViolation.md): Result: Last measured length of the wake-up request
- [ChkStart_LINWakeupRetryViolation](CAPLfunctionChkStartLinWakeupRetryViolation.md): Result: Last measured timeout between two consecutive LIN WakeUp signals

## Example

```plaintext
long result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
  result = ChkQuery_EventInterval_AsyncResult(checkId);
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
