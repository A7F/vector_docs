# C2xIsScenarioStarted

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xIsScenarioStarted.md)

**CAPL Functions** » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xIsScenarioStarted

**Valid for**: CANoe DE

## Function Syntax

```
long C2xIsScenarioStarted();
```

## Description

This function checks if the scenario assigned to the current CANoe DE product configuration is in the running state. The scenario can be started:

- Manually in Scenario Manager Window
- As a result of calling [C2xStartScenario()](CAPLfunctionC2xStartScenario.md) CAPL function.

## Parameters

—

## Return Values

- **1**: Scenario was started (is running now).
- **0**: Scenario is not running now.
- **-1**: Error

## Example

—
