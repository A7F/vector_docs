# OnScenarioStateChanged (Callback)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void OnScenarioStateChanged(long newState);
```

## Description

This callback function is called when the state of the scenario was changed in Scenario Manager Window or by calling Scenario API CAPL functions.

## Parameters

- **newState**: Current state of the scenario
  - 0: Loaded – The scenario file was successfully loaded as a result of C2xLoadScenario() CAPL function call
  - 1: Started – Scenario was started (in Scenario Manager window or by C2xStartScenario() function call)
  - 2: Stopped - Scenario was stopped (in Scenario Manager or by C2xStopScenario() function call)
  - 3: Completed – Scenario has reached the end of its timeline defined in the scenario file.

## Return Values

—

## Example

```plaintext
void OnScenarioStateChanged(long newState)
{
  write ("New state %d", newState);
}
```
