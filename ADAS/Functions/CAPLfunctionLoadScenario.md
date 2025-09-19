# LoadScenario

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » LoadScenario

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This CAPL function is also available as C# function.

## Function Syntax

**C#**  
`bool LoadScenario.Call(string path);`

**CAPL**  
`int LoadScenario.Call(char[] path);`

## Description

Loads a scenario during a running measurement via a file path.

## Parameters

- **path**: Path to the scenario which shall be loaded.

## Return Values

**C#**

- **true**: Scenario could be loaded
- **false**: Scenario could not be loaded (check for correct path)

**CAPL**

- **1**: Scenario could be loaded
- **0**: Scenario could not be loaded (check for correct path)

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```plaintext
int result = ScenarioManager.LoadScenario.Call("YourPath\\YourScenario.scn");
```

### C#

```plaintext
bool result = ScenarioManager.LoadScenario.Call("YourPath\\YourScenario.scn");
```
