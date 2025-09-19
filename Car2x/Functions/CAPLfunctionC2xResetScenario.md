# C2xResetScenario

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long C2xResetScenario()
```

## Description

If the current scenario is running, it must be stopped via [C2xStopScenario()](CAPLfunctionC2xStopScenario.md) function call or by stopping scenario in Scenario Manager window before calling C2xLoadScenario function.

This function resets all scenario objects to their original state as defined in the loaded scenario.

## Parameters

—

## Return Values

- **0**: Success
- **≠0**: Error

## Example

```c
on key 's'
{
  C2xStopScenario();
  C2xResetScenario();
}
```
