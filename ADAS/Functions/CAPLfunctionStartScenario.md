# StartScenario

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This CAPL function is also available as C# function.

## Function Syntax

**C#**  
`bool StartScenario.Call();`

**CAPL**  
`int StartScenario.Call();`

## Description

Starts the currently loaded scenario.

## Parameters

—

## Return Values

**C#**

- **true**: Start of scenario was successful
- **false**: Start of scenario failed

**CAPL**

- **1**: Start of scenario was successful
- **0**: Start of scenario failed

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```plaintext
int result = ScenarioManager.StartScenario.Call();
```

### C#

```plaintext
bool result = ScenarioManager.StartScenario.Call();
```
