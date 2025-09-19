# StopScenario

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This CAPL function is also available as C# function.

## Function Syntax

**C#**  
`bool StopScenario.Call();`

**CAPL**  
`int StopScenario.Call();`

## Description

Stops the currently running scenario.

## Parameters

—

## Return Values

**C#**

- **true**: Stop of scenario was successful
- **false**: Stop of scenario failed

**CAPL**

- **1**: Stop of scenario was successful
- **0**: Stop of scenario failed

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```capl
int result = ScenarioManager.StopScenario.Call();
```

### C#

```csharp
bool result = ScenarioManager.StopScenario.Call();
```
