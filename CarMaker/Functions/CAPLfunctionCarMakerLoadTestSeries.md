# CarMaker_LoadTestSeries

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CarMaker_LoadTestSeries(char testSeries[]);
```

## Description

Loads a test series with the given name within CarMaker. Although [CarMaker_LoadTestRun](CAPLfunctionCarMakerLoadTestRun.md) can also be used to load test series, this function should be preferred. This is because CarMaker may display a warning about unsaved test series that will otherwise interfere with the test.

## Parameters

- **testSeries**: Hierarchical name of the test series.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
// load the test series into CarMaker
gErrorState = CarMaker_LoadTestSeries("Examples/Powertrain/DrivingCycles/DrivingCycles.ts");
```
