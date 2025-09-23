# ChkQuery_StatProbeIntervalMax_AsyncResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double ChkQuery_StatProbeIntervalMax_AsyncResult(dword aCheckId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
check.QueryStatProbeIntervalMaxAsyncResult();
```

## Description

Returns the maximum timely distance between 2 consumed message events.

**Note**: Among other things with this function this function the maximum occurred cycle time of a cyclic message can be queried.

The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
  - **Note**: There is a meaningful value available and a positive return value is supplied even if the check has not generated any event.
- **\> 0**: Maximum timely distance

## Example

```plaintext
long result;
dword checkId;
double statProbe;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
  statProbe = ChkQuery_StatProbeIntervalMax_AsyncResult(checkId);
```
