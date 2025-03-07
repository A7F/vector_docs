[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetReferencePoint.md)

**CAPL Functions** » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xGetReferencePoint

# C2xGetReferencePoint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long C2xGetReferencePoint(char* refPointName, out float latitude, out float longitude)` //form 1
- `long C2xGetReferencePoint(int refPointID, out float latitude, out float longitude)` //form 2

## Description

This function gets the latitude and longitude position of the specified reference point.

## Parameters

- **refPointName (form 1)**: Name of the scenario reference point.
- **refPointID (form 2)**: ID of the scenario reference point.
- **latitude**: The latitude value of the point as float value.
- **longitude**: The longitude value of the point as float value.

## Return Values

- **0**: Success
- **-1**: Reference Point not found

## Example

```plaintext
on key 's'
{
  float refPointLat, refPointLng;

  C2xLoadRoute("MyRouteFile.kml", "MyCustomRoute",0);
  C2xSetStationsOnRoute("DuT_Route","MyCustomRoute");
  C2xSetRouteStartPoint("MyCustomRoute", "DuT", @GNSS::Ath1.Latitude, @GNSS::Ath1.Longitude, @GNSS::Ath1.Direction);
  C2xMoveRouteRelativeToRefPoint("EVA_Route", "MyCustomRoute", "CollisionPoint1", "Sender_EVA");

  C2xGetReferencePoint("CollisionPoint1", refPointLat,refPointLng);
  write("CollisionPoint1 is now at (%f, %f)", refPointLat, refPointLng);

  C2xStartScenario();
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)