# C2xGetStationPropertyDouble

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
float C2xGetStationPropertyDouble(char* propertyName); // form 1
float C2xGetStationPropertyDouble(char* stationName, char* propertyName); // form 2
```

## Description

This function returns the value of a station property of type float that was assigned in a V2x scenario.

## Parameters

- **stationName**: Name of the station
- **propertyName**: Name of the station’s property

  Possible property values are:
  - Latitude
  - Longitude
  - Elevation
  - Heading
  - Acceleration
  - YawRate
  - Length
  - Width
  - Height

## Return Values

- **Value**: Value of type double
- **-1**: Error

## Example

```plaintext
on start
{
  float width, height;
  width = C2xGetStationPropertyDouble("Station1", "Width");
  height = C2xGetStationPropertyDouble("Station1", "Height");
}
```
