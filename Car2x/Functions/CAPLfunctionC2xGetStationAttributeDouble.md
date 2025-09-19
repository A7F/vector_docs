# C2xGetStationAttributeDouble

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `float C2xGetStationAttributeDouble(char[] attributeName); // form 1`
- `float C2xGetStationAttributeDouble(char[] stationName, char[] attributeName); // form 2`

## Description

This function returns the actual value of the floating point typed scenario attribute. Form 1 of the function returns values of an attribute of the calling (current) station. Form 2 allows to get values of all attributes of any station in the scenario, even if the scenario station does not have an assigned database node.

## Parameters

- **stationName**: Scenario station name
- **attributeName**: Name of the scenario attribute which belongs to the scenario station specified by stationName parameter.

## Return Values

The floating point value of the attribute at the time of function call.

- **-1**: Error, specified station and/or attribute name do not exist in the scenario.

## Example

```c
void OnStartScenario()
{
  write("OnStartScenario - Station Speed = %f", C2xGetStationAttributeDouble("Speed"));
}

void OnStationAttributeTrigger(char attrName[])
{
  if (strncmp(attrName,"Speed",strlen(attrName)) == 0)
  {
    write("%f sec : Speed = %f",
          TimeNowNS()/1e9,
          C2xGetStationAttributeDouble("Speed"));
  }
}

on key 'c'
{
  write("OnStartScenario - Station Latitude = %f", C2xGetStationAttributeDouble("Latitude"));
  write("OnStartScenario - Station Longitude = %f", C2xGetStationAttributeDouble("Longitude"));
}
```
