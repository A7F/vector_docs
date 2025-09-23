# ChkQuery_Precision

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
double ChkQuery_Precision (dword aCheckId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```c
check.QueryPrecision();
```

## Description

Returns a factor that can be multiplied with the return value of the statistical queries to convert the time stamp to the standard unit milliseconds.

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **double**: 100 to 10^-6

## Example

```c
double result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_Precision(checkId);
```

[ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md)
