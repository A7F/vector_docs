[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSetStationAttributeDouble.md)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xSetStationAttributeDouble

# C2xSetStationAttributeDouble

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long C2xSetStationAttributeDouble(char stationName[], char attributeName[], long keypointIndex, double value)` // form 1
- `long C2xSetStationAttributeDouble(char attributeName[], long keypointIndex, double value)` // form 2
- `Int64 C2xSetStationAttributeDouble(char* attributeName, float value);` // form 3
- `Int64 C2xSetStationAttributeDouble(char* stationName, char* attributeName, float value);` // form 4

## Description

- **Form 1-2**: Sets an attribute value for a scenario station and a particular keypoint as double.
- **Form 3-4**: Sets the floating point value for a station’s attribute. Internally a keypoint is created at the current point in time.

## Parameters

### Form 1-2

- **stationName**: Name of the station.
- **attributeName**: Name of the attribute in the station’s timeline.
- **keypointIndex**: The Keypoint index of the attribute (starts at 0).
- **value**: The value to be set.

### Form 3-4

- **stationName**: Name of the station.
- **attributeName**: Name of the attribute in the station’s timeline.
- **value**: The value to be set.

## Return Values

### Form 1-2

- **0**: Success
- **≠0**: Error occurred

### Form 3-4

- **0**: OK
- **-1**: Error

## Example

**Example for Form 1-2**

```plaintext
on start
{
  // Set the first speed keypoint to 50 km/h
  C2xSetStationAttributeDouble("DuT", "Speed", 0, 50);
}
```

**Example for Form 3-4**

```plaintext
C2xSetStationAttributeDouble("Station1", "MyDoubleAttr", 1.5);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)