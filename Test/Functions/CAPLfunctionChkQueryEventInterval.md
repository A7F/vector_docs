# ChkQuery_EventInterval

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ChkQuery_EventInterval (dword checkId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
check.QueryEventInterval();
```

## Description

Returns the last time-interval that has led to the event.

## Parameters

- **checkId**: Identifier of the queried Check.

## Return Values

- **-101**: The interval for the last event has been started but not yet terminated.
- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md) in this chapter.
- **≥ 0**: Time interval in the precision of the check.

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

```c
long result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_EventInterval(checkId);
Write("result = %d", result);
```
