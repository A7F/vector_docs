[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetStationPropertyInt64.md)

**CAPL Functions** » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xGetStationPropertyInt64

# C2xGetStationPropertyInt64

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
int64 C2xGetStationPropertyInt64(char* propertyName); // form 1
int64 C2xGetStationPropertyInt64(char* stationName, char* propertyName); // form 2
```

## Description

This function returns the value of a station property of type int64 that was assigned in a V2x scenario.

## Parameters

- **stationName**: Name of the station.
- **propertyName**: Name of the station’s property. Possible property values are:
  - StartOffset
  - ID

## Return Values

- **Value**: Value of type int64
- **-1**: Error

## Example

```plaintext
on start
{
  int64 result;
  result = C2xGetStationPropertyInt64("Station1", "StartOffset");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)