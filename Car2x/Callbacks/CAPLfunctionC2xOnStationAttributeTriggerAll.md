# OnStationAttributeTriggerAll (Callback)

**Valid for**: CANoe DE

## Function Syntax

```c
void OnStationAttributeTriggerAll(char stationName[], char attributeName[]);
```

## Description

This callback is called when the following two conditions are met:

- The scenario attribute with the name specified in `attributeName` reaches the next attribute keypoint (value assignment) in the timeline of a scenario station with the name specified in `stationName`.
- Scenario attribute property **Trigger** was set to true in the corresponding scenario file.

The purpose of this callback is to define a reaction on all triggerable attributes of all stations in the scenario. If you only want to react on the attribute triggering of the station’s own attributes only, please use [OnStationAttributeTrigger](CAPLfunctionC2xOnStationAttributeTrigger.md) callback function instead.

## Parameters

- **stationName**: Name of the scenario station
- **attributeName**: Name of the scenario station attribute

## Return Values

—

## Example

```c
void OnStationAttributeTriggerAll(char stationName[], char attributeName[])
{
    // For all trigger attributes of all stations in the scenario
    write("CAPL Node '%NODE_NAME%', Car2x/V2x station '%s', %f sec : OnStationAttributeTriggerAll called - Attribute '%s' = %f" ,
          stationName,
          TimeNowNS()/1e9 ,
          attributeName,
          C2xGetStationAttributeDouble(stationName, attributeName));

    // For concrete trigger attribute of a some known station "Station1"
    if (strncmp(stationName,"Station1",strlen(stationName)) == 0 &&
        strncmp(attributeName,"Speed",strlen(attributeName)) == 0)
    {
        write("Car2x/V2x Station '%s', %f sec : OnStationAttributeTriggerAll called - Station1 Speed = %f",
              stationName,
              TimeNowNS()/1e9 ,
              C2xGetStationAttributeDouble(stationName, "Speed"));
    }
}
```
