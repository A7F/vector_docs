[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSaddwpmeander.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSAddWpMeander**

# GNSSAddWpMeander

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword GNSSAddWpMeander(double latitudeRef, double longitudeRef, double altitudeRef, double width, double height, double radius, dword numOfLoops);
```

## Description

This function can be used to describe a meander with rounded off corners. To do this, the points that describe the meander are inserted at the end of the waypoint list. The unit of the parameters depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

The following illustrations describe the effect of the prefixed sign on the values for height and width (assuming that radius = 0). The thicker point identifies the reference point.

## Parameters

- **latitudeRef**: latitude of the reference point (in degrees)
- **longitudeRef**: longitude of the reference point (in degrees)
- **altitudeRef**: altitude of the reference point (in m or ft)
- **width**: width (w) of a loop (in m or yd). Direction is west to east or east to west.
- **height**: height (h) of a loop (in m or yd). Direction is north to south or south to north.
- **radius**: radius (r) of the rounded off corners of the loop (in m or yd)
- **numOfLoops**: number of loops

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```plaintext
// meander with 3 loops, every loop has a width of 100 yd and a height of 200 yd
GNSSSetUnits(1);
GNSSAddWpMeander(48.46, 9.11, 225, 100, 200, 10, 3);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
