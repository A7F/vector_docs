# C2xGetStationPosition

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xGetStationPosition(out float latitude, out float longitude, out float elevation, out float heading); // form 1
long C2xGetStationPosition(char* stationName, out float latitude, out float longitude, out float elevation, out float heading); //form 2
```

## Description

This function returns the position and heading of a station as out parameters.

## Parameters

- **stationName**: Name of the station defined in a scenario.
- **latitude**: Latitude of the station as float value.
- **longitude**: Longitude of the station as float value.
- **elevation**: Elevation of the station as float value.
- **heading**: Heading of the station as float value (degrees).

## Return Values

- **0**: OK
- **-1**: Error

## Example

```plaintext
on key ‘p’
{
  float latitude, longitude, elevation, heading;
  long result;
  result = C2xGetStationPosition("station1", latitude, longitude, elevation, heading);
}
```
