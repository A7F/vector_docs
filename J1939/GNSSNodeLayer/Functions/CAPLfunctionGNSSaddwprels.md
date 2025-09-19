[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSaddwprels.md)

## CAPL Functions » J1939 » GNSS NL » GNSSAddWpRels

### Function Syntax

```
dword GNSSAddWpRels(double latLength, double lonLength, double altLength, double speed)
```

### Description

This function inserts a new waypoint at a given speed at the end of the waypoint list. The new point is derived by adding the path differences and the last waypoint to be inserted.

When the new waypoint is reached, the GNSS receiver moves on at the assigned speed. The speed will be maintained until a waypoint with another speed is reached or the speed is changed by the [GNSSSetSpeed](CAPLfunctionGNSSsetspeed.md) function.

The unit of the parameters depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

### Parameters

- **latLength**: difference in length along the latitude in reference to the last waypoint to be inserted (in m or yd)
  - positive value: eastward
  - negative value: westward
- **lonLength**: difference in length along the longitude in reference to the last waypoint to be inserted (in m or yd)
  - positive value: northward
  - negative value: southward
- **altLength**: difference in altitude in terms of the last waypoint to be inserted (in m or yd)
- **speed**: speed of the GNSS receiver (in km/h, mph or kn)

### Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

### Example

```c
// set a waypoint
GNSSAddWaypoint(54.0, 8.0, 0);

// add a new waypoint 200 yd southerly of the last waypoint and set a new speed of 10 kn when this waypoint is reached
GNSSSetUnits(2);
GNSSAddWpRels(0.0, -200.0, 0, 10);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
