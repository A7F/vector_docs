# ChkQuery_Precision_AsyncResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
double ChkQuery_Precision_AsyncResult(dword aCheckId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```c
check.QueryPrecisionAsyncResult();
```

## Description

Returns a factor that can be multiplied with the return value of the statistical queries to convert the time stamp to the standard unit milliseconds.

The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **CheckId**: Identifier of the queried Check.

## Return Values

- **double**: 100 to 10^-6

## Example

```c
long result;
dword checkId;
double precision;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
  precision = ChkQuery_Precision_AsyncResult(checkId);
```
