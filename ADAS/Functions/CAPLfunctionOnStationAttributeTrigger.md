[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionOnStationAttributeTrigger.md)

## OnStationAttributeTrigger

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » OnStationAttributeTrigger

**Valid for:** CANoe DE

**Note:** This CAPL function is also available in C#.

### Function Syntax

**C#**

```csharp
void OnStationAttributeTrigger(_ADAS.DataModel.IScenarioManager_Types.OnStationAttributeTrigger.TransientCallContext cct)
```

**CAPL**

```capl
void OnStationAttributeTrigger ()
```

### Description

This callback is called when the value of an attribute of a station has changed.

### Parameters

**C#**

- **tcc**: Call Context of the Callback. Contains the station name (`cct.stationName`) and the attribute name (`cct.attributeName`).

**CAPL**

- —

### Return Values

- —

### Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

#### CAPL

```capl
on fct_called ADAS::ScenarioManager.OnStationAttributeTrigger
{
  write("Attribute trigger: %s, %s", this.stationName, this.attributeName);
}
```

#### C#

```csharp
[OnCalled(ScenarioManager.MemberIDs.OnStationAttributeTrigger)]
public void OnStationAttributeTrigger(_ADAS.DataModel.IScenarioManager_Types.OnStationAttributeTrigger.TransientCallContext cct)
{
  Output.WriteLine(String.Format("Attribute trigger: {0}, {1}", cct.stationName, cct.attributeName));
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
