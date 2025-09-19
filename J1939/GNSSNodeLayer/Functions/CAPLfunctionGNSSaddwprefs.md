[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSaddwprefs.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSAddWpRefS**

# GNSSAddWpRefS

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSAddWpRefS( double latLength, double lonLength, double altLength, double speed )
```

## Description

This function inserts a new waypoint at a given speed at the end of the waypoint list. The new point is derived by adding the path differences and the last waypoint to be set by [GNSSSetRefPoint](CAPLfunctionGNSSsetrefpoint.md).

When the new waypoint is reached, the GNSS receiver moves on at the assigned speed. The speed will be maintained until a waypoint with another speed is reached or the speed is changed by the [GNSSSetSpeed](CAPLfunctionGNSSsetspeed.md) function.

The unit of the parameters depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

- **latLength**: difference in length along the latitude in respect to the reference point (in m or yd)
  - positive value: eastward
  - negative value: westward

- **lonLength**: difference in length along the longitude in respect to the reference point (in m or yd)
  - positive value: northward
  - negative value: southward

- **altLength**: difference in altitude with respect to the reference point (in m or yd)

- **speed**: speed of the GNSS receiver (in km/h, mph or kn)

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
// set a reference point
GNSSSetRefPoint( 48.46, 9.11, 225 );

// add a new waypoint 50 yd southerly and 30 yd westerly of the reference point and set a new speed of 35 mph when this waypoint is reached
GNSSSetUnits( 1 );
GNSSAddWpRefS( -30.0, -50.0, 0, 35 );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
