[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CarMaker/Functions/CAPLfunctionCarMakerLoadTestSeries.md)

[CAPL Functions](../../CAPLfunctions.md) » [CarMaker Interface](../CAPLfunctionsCarMakerOverview.md) » CarMaker_LoadTestSeries

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)