# testWaitForValueChangePropagation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long testWaitForValueChangePropagation();
```

## Description

Wait until value changes for system variables or value entities have been propagated through the simulation loop. This is especially important if the [asynchronous evaluation](../../../CANoeCANalyzer/Ribbon/File/Options/Measurement/MeasurementPerformanceAsyncBackgroundCheck.md) of constraints and conditions is activated.

## Parameters

—

## Return Values

- **-1**: General error, for example, functionality is not available.
- **0**: Wait successful

## Example

```plaintext
@vars::var1 = 3;
testWaitForValueChangePropagation();
// create checks, add constraints
```
