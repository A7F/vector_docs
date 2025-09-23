# ChkQuery_StatEventFreePeriodMed_AsyncResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
double ChkQuery_StatEventFreePeriodMed_AsyncResult(dword aCheckId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```c
check.QueryStatEventFreePeriodMedAsyncResult();
```

## Description

Returns the average timely distance between events and check starts/stops. The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **≥ 0**: Average timely distance in the current precision

## Example

```c
long result;
dword checkId;
double period;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
  period = ChkQuery_StatEventFreePeriodMed_AsyncResult(checkId);
```
