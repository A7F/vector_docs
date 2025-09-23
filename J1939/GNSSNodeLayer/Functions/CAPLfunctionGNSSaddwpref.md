[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSaddwpref.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSAddWpRef**

# GNSSAddWpRef

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSAddWpRef( double latLength, double lonLength, double altLength )
```

## Description

This function inserts a new waypoint at the end of the waypoint list. The new point is derived by adding the path differences and the last waypoint to be set by [GNSSSetRefPoint](CAPLfunctionGNSSsetrefpoint.md).

The unit of the parameters depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

- **latLength**: difference in length along the latitude in respect to the reference point (in m or yd)
  - positive value: eastward
  - negative value: westward

- **lonLength**: difference in length along the longitude in respect to the reference point (in m or yd)
  - positive value: northward
  - negative value: southward

- **altLength**: difference in altitude with respect to the reference point (in m or yd)

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
// set reference point
GNSSSetRefPoint( 48.46, 9.11, 255.0 );

// add a new waypoint 150 meter northly of the reference point
GNSSSetUnits( 0 );
GNSSAddWpRef( 0.0, 150.0, 0.0 );
```
