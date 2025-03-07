[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionSetStationAttributeInt64.md)

# SetStationAttributeInt64

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » SetStationAttributeInt64

Valid for: CANoe DE

**Note**  
This CAPL function is also available in C#.

## Function Syntax

**C#**  
`bool SetStationAttributeInt64.Call(string stationName, string attribute, int32 keypointIndex, int64 value);`

**CAPL**  
`int SetStationAttributeInt64.Call(char[] stationName, char[] attribute, int keypointIndex, int64 value);`

## Description

Sets values for attributes based on the attribute name and keypoint (index) in the Scenario Editor timeline.

## Parameters

- **stationName**: The name of the station for which the attribute shall be set.
- **attribute**: The name of the attribute which shall be set. There are no default int64 attributes, user-defined values must be created first in the Scenario Editor timeline.
- **keypointIndex**: An attribute may have several keypoints in the Scenario Editor timeline. This parameter allows to set different values for each keypoint. Starts with 0 (First keypoint has index 0, second keypoint has index 1, … )
- **value**: The value to be set.

## Return Values

**C#**

- **true**: Set was successful.
- **false**: Set failed. Check for incorrect attribute name.

**CAPL**

- **1**: Set was successful.
- **0**: Set failed. Check for incorrect attribute name.

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```c
// Set the UserDefinedInt64Val for the station DuT to the value 5 for the 3rd keypoint
int result = ScenarioManager.SetStationAttributeInt64.Call("DuT", "UserDefinedInt64Val", 2, 5);
```

### C#

```csharp
// Set the UserDefinedInt64Val for the station DuT to the value 5 for the 3rd keypoint
bool result = ScenarioManager.SetStationAttributeInt64.Call("DuT", "UserDefinedInt64Val", 2, 5);
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)