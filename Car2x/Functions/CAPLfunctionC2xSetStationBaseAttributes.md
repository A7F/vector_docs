# C2xSetStationBaseAttributes

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

`Int64 C2xSetStationBaseAttributes(char* stationName, float latitude, float longitude, float elevation, float direction, float speed);`

## Description

Assigns the data latitude, longitude, direction and speed to a dynamically added station of a scenario.

## Parameters

- **stationName**: Name of the station.
- **Latitude**: Latitude of the station (multiplier 10000000.0).
- **Longitude**: Longitude of the station (multiplier 10000000.0).
- **Elevation**: Elevation of the station.
- **Direction**: Heading in euler degrees.
- **Speed**: Speed in m/s.

## Return Values

- **0**: OK
- **-1**: Error

## Example

```c
// In this example GPS data is received via System-variables and assigned to the station.
on sysvar GPS::GPS1
{
  C2xSetStationBaseAttributes("Station1",
  @GPS::GPS1.Latitude * 10000000.0,
  @GPS::GPS1.Longitude * 10000000.0,
  @GPS::GPS1.Altitude,
  @GPS::GPS1.Direction,
  @GPS::GPS1.Speed);
}
```
