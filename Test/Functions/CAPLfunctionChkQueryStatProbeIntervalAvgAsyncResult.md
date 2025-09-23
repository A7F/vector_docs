# ChkQuery_StatProbeIntervalAvg_AsyncResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
double ChkQuery_StatProbeIntervalAvg_AsyncResult(dword aCheckId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```c
check.QueryStatProbeIntervalAvgAsyncResult();
```

## Description

Returns the average timely distance between 2 consumed message events. The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
  - **Note**: There is a meaningful value available and a positive return value is supplied even if the check has not generated any event.
- **\> 0**: Average timely distance

## Example

```c
long result;
dword checkId;
double statProbe;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
  statProbe = ChkQuery_StatProbeIntervalAvg_AsyncResult(checkId);
```
