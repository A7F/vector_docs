[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionOnScenarioStateChange.md)

# OnScenarioStateChange

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » OnScenarioStateChange

**Valid for**: CANoe DE

**Note**: This CAPL function is also available in C#.

## Function Syntax

**C#**

```csharp
void OnScenarioStateChange(_ADAS.DataModel.IScenarioManager_Types.OnScenarioStateChange.TransientCallContext cct)
```

**CAPL**

```capl
void OnScenarioStateChange()
```

## Description

Is called when the state of the scenario has changed. State values:

- 0: Loaded
- 1: Started
- 2: Stopped
- 3: Completed

## Parameters

**C#**

- **tcc**: Call Context of the Callback. Contains the state of the Scenario (cct.state)

**CAPL**

- —

## Return Values

- —

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```capl
/on fct_called ADAS::ScenarioManager.OnScenarioStateChange
{
  write("Current scenario state: %i", this.state);
}
```

### C#

```csharp
[OnCalled(ScenarioManager.MemberIDs.OnScenarioStateChange)]
public void OnScenarioStateChange(_ADAS.DataModel.IScenarioManager_Types.OnScenarioStateChange.TransientCallContext cct)
{
  Output.WriteLine("Current scenario state: " + cct.state);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)