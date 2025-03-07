[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetStationPosition.md)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xGetStationPosition

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)