# ChkQuery_EventTimestamp64_AsyncResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
Int64 ChkQuery_EventTimestamp64_AsyncResult(dword CheckId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
check.QueryEventTimestamp64AsyncResult();
```

## Description

Retrieves time stamp of last fired event. The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **CheckId**: Identifier of the queried Check.

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **\> 0**: Event time stamp in units set for the queried Check with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md)

## Example

```c
Int64 result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
  result = ChkQuery_EventTimestamp64_AsyncResult(checkId);
```
