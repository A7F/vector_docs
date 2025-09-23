[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSsetrefpoint.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSSetRefPoint**

# GNSSSetRefPoint

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSSetRefPoint( double latitude, double longitude, double altitude )
```

## Description

This function defines a reference point that will be used by the functions [GNSSAddWpRef](CAPLfunctionGNSSaddwpref.md) and [GNSSAddWpRefS](CAPLfunctionGNSSaddwprels.md) to calculate a new waypoint. The unit of the altitude parameter depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

- **latitude**: latitude of the reference point in degrees
- **longitude**: longitude of the reference point in degrees
- **altitude**: altitude of the reference point (in m or ft)

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
GNSSSetRefPoint( 48.46, 9.11, 225.0 );
```
