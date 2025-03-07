[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSetStationBaseAttributes.md)

**CAPL Functions** » **Car2x** » **C2xSetStationBaseAttributes**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)