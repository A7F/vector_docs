[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSaddwprect.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSAddWpRect

# GNSSAddWpRect

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSAddWpRect( double latitudeRef, double longitudeRef, double altitudeRef, double width, double height, double radius );
```

## Description

This function can be used to describe a rectangle with rounded off corners. To do this, the points that describe the rectangle are inserted at the end of the waypoint list. The unit of the parameters depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

The following illustrations describe the effect of the prefixed sign on the values for height and width (assuming that radius = 0). The thicker point identifies the reference point.

**Special case:** If the height and width are both identical to one half the radius, the result is a circle.

## Parameters

- **latitudeRef**: latitude of the reference point (in degrees)
- **longitudeRef**: longitude of the reference point (in degrees)
- **altitudeRef**: altitude of the reference point (in m or ft)
- **width**: width (w) of the rectangle (in m or yd)
- **height**: height (h) of the rectangle (in m or yd)
- **radius**: radius (r) of the rounded off corners of the rectangle (in m or yd)

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
// slotted hole with width of 400 yd and height of 200 yd
GNSSSetUnits( 1 );
GNSSAddWpRect( 48.46, 9.11, 225, 400, 200, 100 );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
