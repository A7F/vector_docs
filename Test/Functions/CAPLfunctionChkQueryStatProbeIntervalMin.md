# ChkQuery_StatProbeIntervalMin

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double ChkQuery_StatProbeIntervalMin (dword aCheckId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.QueryStatProbeIntervalMin();
```

## Description

Returns the minimum timely distance between 2 consumed message events.

**Note**: Among other things with this function, the minimum occurred cycle time of a cyclic message can be queried.

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)

  **Note**: There is a meaningful value available and a positive return value is supplied even if the check has not generated any event.

- **\> 0**: Minimum timely distance

## Example

```plaintext
double result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_StatProbeIntervalMin(checkId);
```
