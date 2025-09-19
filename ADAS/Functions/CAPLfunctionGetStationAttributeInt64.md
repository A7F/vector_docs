# GetStationAttributeInt64

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This CAPL function is also available in C#.

## Function Syntax

**C#**  
`int64 GetStationAttributeInt64.Call(string stationName, string attribute);`

**CAPL**  
`int64 GetStationAttributeInt64.Call(char[] stationName, char[] attribute);`

## Description

Queries an attribute of a scenario as a value of type int64 at the runtime of the scenario.

## Parameters

- **stationName**  
  The name of the station from which the attribute shall be got.

- **attribute**  
  The name of the attribute which shall be got. Available default (int64) attributes:
  - ID
  - StartOffset

  Further user-defined attributes can be created in the Scenario Editor timeline.

## Return Values

**C#**  
- The value of the attribute.
- **0**  
  The value of the attribute cannot be found.

**CAPL**  
- The value of the attribute.
- **0**  
  The value of the attribute cannot be found.

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```plaintext
int64 userDef = ScenarioManager.GetStationAttributeInt64.Call("DuT", "UserDefinedInt64Val");
```

### C#

```plaintext
int64 userDef = ScenarioManager.GetStationAttributeInt64.Call("DuT", "UserDefinedInt64Val");
```
