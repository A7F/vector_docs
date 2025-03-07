[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSetStationAttributeInt64.md)

[C2xSetStationAttributeInt64](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xSetStationAttributeInt64

# C2xSetStationAttributeInt64

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long C2xSetStationAttributeInt64(char stationName[], char attributeName[], long keypointIndex, int64 value)` // form 1
- `long C2xSetStationAttributeInt64(char attributeName[], long keypointIndex, int64 value)` // form 2
- `Int64 C2xSetStationAttributeInt64(char* attributeName, Int64 value);` // form 3
- `Int64 C2xSetStationAttributeInt64(char* stationName, char* attributeName, Int64 value);` // form 4

## Description

- **Form 1-2**: Sets an attribute value for a scenario station and a particular keypoint as Int64.
- **Form 3-4**: Sets the 64-bit integer value for a station’s attribute. Internally a keypoint is created at the current point in time.

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
  // Set the first lights keypoint to 1
  C2xSetStationAttributeInt64("DuT", "R_Light", 0, 1);
}
```

**Example for Form 3-4**

```plaintext
// Activate Roadworks Warning
on key 'a'
{
  C2xSetStationAttributeInt64("Events_Vehicle_Events_DENM1::EventPosAndTime", 1);
  C2xSetStationAttributeInt64("Events_Vehicle_Events_DENM1::CauseCode", 3);
  C2xSetStationAttributeInt64("Events_Vehicle_Events_DENM1::SubCauseCode", 0);
  C2xSetStationAttributeInt64("Events_Vehicle_Events_DENM1::ActionIdOriginatingStationId", 0);
  C2xSetStationAttributeInt64("Events_Vehicle_Events_DENM1::ActionIdSequenceNumber", 1);
  C2xSetStationAttributeInt64("Events_Vehicle_Events_DENM1", 1);
}

// De-Activate Roadworks Warning
on key 'b'
{
  C2xSetStationAttributeInt64("Events_Vehicle_Events_DENM1", 0);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)