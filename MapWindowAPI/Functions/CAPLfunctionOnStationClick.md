# OnStationClick

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`OnStationClick(long stationHandle);`

## Description

Function is called when a station in the Map window is clicked.

## Parameters

- **stationHandle**: Handle of the station in the map window.

## Return Values

- **0**: Success
- **≠0**: Error

## Example

```c
void OnStationClick(long stationHandle)
{
    char stationName[1024];
    if (C2xGetStationName(stationHandle, elcount(stationName), stationName) == 0)
    {
        write("Station: %s", stationName);
        write("Station handle: %d", stationHandle);
    }
}
```
