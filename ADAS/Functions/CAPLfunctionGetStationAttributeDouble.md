[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionGetStationAttributeDouble.md)

## CAPL Functions » ADAS » GetStationAttributeDouble

### GetStationAttributeDouble

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: This CAPL function is also available as C# function.

### Function Syntax

**C#**

```csharp
double GetStationAttributeDouble.Call(string stationName, string attribute);
```

**CAPL**

```capl
double GetStationAttributeDouble.Call(char[] stationName, char[] attribute);
```

### Description

Queries an attribute of a scenario as a value of type double at the runtime of the scenario.

### Parameters

- **stationName**: The name of the station from which the attribute shall be got.
- **attribute**: The name of the attribute which shall be got. Available default (double) attributes:
  - Latitude
  - Longitude
  - Heading
  - Elevation
  - Acceleration
  - Length
  - Width
  - Height
  - Distance

Further user-defined attributes can be created in the Scenario Editor timeline.

### Return Values

**C#**

- The value of the attribute.
- **0**: The value of the attribute cannot be found.

**CAPL**

- The value of the attribute.
- **0**: The value of the attribute cannot be found.

### Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

#### CAPL

```capl
double latitude = ScenarioManager.GetStationAttributeDouble.Call("DuT", "Latitude");
```

#### C#

```csharp
double latitude = ScenarioManager.GetStationAttributeDouble.Call("DuT", "Latitude");
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
