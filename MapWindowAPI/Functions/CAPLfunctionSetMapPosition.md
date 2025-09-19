[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MapWindowAPI/Functions/CAPLfunctionSetMapPosition.md)

**CAPL Functions** » **Map Window API** » **SetMapPosition**

# SetMapPosition

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapPosition( float latitude, float longitude );
```

## Description

Sets the map to a specific position.

**Note**: If the [Auto-Follow option](../../../CANoeCANalyzer/Windows/Map/MapWindowGui.md) is enabled for a vehicle, the option will be disabled.

## Parameters

- **latitude**: Latitude of the position where the map should jump.
- **longitude**: Longitude of the position where the map should jump.

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

```plaintext
void SetMapPosition()
{
  float lat = 48.824990;
  float lon = 9.094568;

  SetMapPosition(lat, lon);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
