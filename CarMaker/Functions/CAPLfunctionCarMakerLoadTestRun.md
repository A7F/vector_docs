# CarMaker_LoadTestRun

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long CarMaker_LoadTestRun(char testRun[]);
```

## Description

Loads a test run with the given name within CarMaker.

## Parameters

- **testRun**: Hierarchical name of the test run.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
// load the test run configuration into CarMaker
gErrorState = CarMaker_LoadTestRun("Examples/Powertrain/DrivingCycles/EU/NEDC");
```
