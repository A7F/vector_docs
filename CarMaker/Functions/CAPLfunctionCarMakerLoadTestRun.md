[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CarMaker/Functions/CAPLfunctionCarMakerLoadTestRun.md)

[CAPL Functions](../../CAPLfunctions.md) » [CarMaker Interface](../CAPLfunctionsCarMakerOverview.md) » CarMaker_LoadTestRun

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)