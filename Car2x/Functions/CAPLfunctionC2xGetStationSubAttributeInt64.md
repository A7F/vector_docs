# C2xGetStationSubAttributeInt64

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xGetStationSubAttributeInt64

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
float C2xGetStationSubAttributeInt64(char[] attributeName, char[] subAttributeName); // form 1
float C2xGetStationSubAttributeInt64(char[] stationName, char[] attributeName, char[] subAttributeName); // form 2
```

## Description

This function returns the actual value of the integer-typed scenario sub-attribute.  
Form 1 of the function returns values of a sub-attribute of the calling (current) station.  
Form 2 allows to get values of all sub-attributes of any station in the scenario, even if the scenario station does not have an assigned database node.

## Parameters

- **stationName**: Scenario station name
- **attributeName**: Name of the scenario attribute which belongs to the scenario station specified by stationName parameter
- **subAttributeName**: Name of the scenario sub-attribute which belongs to the scenario station attribute specified by attributeName parameter

## Return Values

The integer value of the attribute at the time of function call.

- **-1**: Error, specified station and/or attribute name do not exist in the scenario.

## Example

```plaintext
void OnStartScenario()
{
  write("OnStartScenario - Station Sub Attribute = %d", C2xGetStationSubAttributeInt64("Events_EEBL1", " CauseCode"));
  write("OnStartScenario - Station Sub Attribute = %d", C2xGetStationSubAttributeInt64("Station1", "Events_EEBL1", " CauseCode"));
}
```
