[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSetStationStartOffset.md)

# C2xSetStationStartOffset

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xSetStationStartOffset

**Valid for**: CANoe DE

## Function Syntax

```
long C2xSetStationStartOffset (char* stationName, double startOffset)
```

## Description

If the current scenario is running, it must be stopped via [C2xStopScenario()](CAPLfunctionC2xStopScenario.md) function call or by stopping scenario in Scenario Manager window before calling C2xLoadScenario function.

This function sets the StartOffset of the station defined by stationName to the given value.

## Parameters

- **stationName**: Name of the scenario station
- **startOffset**: StartOffset to be set for the station

## Return Values

- **0**: Success
- **≠0**: Cannot set the offset because scenario is running or station not available.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)