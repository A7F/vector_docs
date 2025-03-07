[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionSetStationAttributeDouble.md)

# SetStationAttributeDouble

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » SetStationAttributeDouble

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This CAPL function is also available in C#.

## Function Syntax

**C#**  
`bool SetStationAttributeDouble.Call(string stationName, string attribute, int32 keypointIndex, double value);`

**CAPL**  
`int SetStationAttributeDouble.Call(char[] stationName, char[] attribute, int keypointIndex, double value);`

## Description

Sets values for attributes based on the attribute name and keypoint (index) in the Scenario Editor timeline.

## Parameters

- **stationName**: The name of the station for which the attribute shall be set.
- **attribute**: The name of the attribute which shall be set. Available default (double) attributes:
  - Latitude
  - Longitude
  - Heading
  - Elevation
  - Acceleration

  Further user-defined attributes can be created in the Scenario Editor timeline.
- **keypointIndex**: An attribute may have several keypoints in the Scenario Editor timeline. This parameter allows to set different values for each keypoint. Starts with 0 (First keypoint has index 0, second keypoint has index 1, … )
- **value**: The value to be set.

## Return Values

**C#**

- **true**: Set was successful
- **false**: Set failed. Check for incorrect attribute name.

**CAPL**

- **1**: Set was successful
- **0**: Set failed. Check for incorrect attribute name.

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```c
// Set the speed for the station DuT to the value 30 km/h for the 5th keypoint
int result = ScenarioManager.SetStationAttributeDouble.Call("DuT", "Speed", 4, 30);
```

### C#

```csharp
// Set the speed for the station DuT to the value 30 km/h for the 5th keypoint
bool result = ScenarioManager.SetStationAttributeDouble.Call("DuT", "Speed", 4, 30);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)