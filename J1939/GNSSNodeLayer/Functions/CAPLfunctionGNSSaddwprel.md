[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSaddwprel.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSAddWpRel

# GNSSAddWpRel

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSAddWpRel( double latLength, double lonLength, double altLength )
```

## Description

This function inserts a new waypoint at the end of the waypoint list. The new point is derived by adding the path differences and the last waypoint to be inserted.

The unit of the parameters depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

- **latLength**: difference in length along the latitude in reference to the last waypoint to be inserted (in m or yd)
  - positive value: eastward
  - negative value: westward

- **lonLength**: difference in length along the longitude in reference to the last waypoint to be inserted (in m or yd)
  - positive value: northward
  - negative value: southward

- **altLength**: difference in altitude in terms of the last waypoint to be inserted (in m or yd)

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
// set a waypoint
GNSSAddWp( 48.46, 9.11, 255 );

// add a new waypoint 200 yd easterly of the last waypoint
GNSSSetUnits( 1 );
GNSSAddWpRel( 200.0, 0.0, 0.0 );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)