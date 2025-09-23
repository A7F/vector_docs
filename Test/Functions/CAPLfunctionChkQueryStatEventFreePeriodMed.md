# ChkQuery_StatEventFreePeriodMed

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
double ChkQuery_StatEventFreePeriodMed (dword aCheckId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```c
check.QueryStatEventFreePeriodMed();
```

## Description

Returns the average timely distance between events and check starts/stops.

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
  - **Note**: There is a meaningful value available and a positive return value is supplied even if the check has not generated any event.
- **≥ 0**: Average timely distance in the current precision

## Example

```c
double result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_StatEventFreePeriodMed(checkId);
```
