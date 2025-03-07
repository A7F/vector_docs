[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetStationPropertyDouble.md)

**CAPL Functions** » **Car2x** » **C2xGetStationPropertyDouble**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)