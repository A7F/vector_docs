[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSaddwps.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSAddWpS**

# GNSSAddWpS

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSAddWpS( double latitude, double longitude, double altitude, double speed )
```

## Description

This function inserts a new waypoint at a given speed at the end of the waypoint list. When this waypoint is reached, the GNSS receiver moves on at the assigned speed. The speed will continue to be used until a waypoint with another speed is reached or the speed is changed by the [GNSSSetSpeed](CAPLfunctionGNSSsetspeed.md) function.

The unit of the parameters speed and altitude depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

- **latitude**: latitude of the new waypoint in degrees
- **longitude**: longitude of the new waypoint in degrees
- **altitude**: altitude of the new waypoint (in m or ft)
- **speed**: speed of the GNSS receiver (in km/h, mph or kn)

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
// stop GNSS receiver if the following waypoint is reached
GNSSAddWpS( 48.46, 9.11, 255.0, 0 );
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
