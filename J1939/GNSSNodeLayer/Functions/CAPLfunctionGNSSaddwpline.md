[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSaddwpline.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSAddWpLine**

# GNSSAddWpLine

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSAddWpLine(double latitude1, double longitude1, double altitude1, double latitude2, double longitude2, double altitude2, dword straightLine)
```

## Description

This function can be used to describe a line. To do this, the points that describe the line are inserted at the end of the waypoint list.

- **StraightLine = 1**  
  The beginning and endpoints are connected by a straight line. In the case of an extended distance, the altitude with respect to the earth ellipsoid changes because of the curvature of the earth. The same result can be obtained by adding two individual way-points (for example with [GNSSAddWp](CAPLfunctionGNSSaddwp.md)).

- **StraightLine = 0**  
  To keep the altitude approximately constant, a number of intermediate points are used by the function. The fixed distance between these intermediate points is about 1000m.

The unit of the parameters `altitude1` and `altitude2` depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

- **latitude1**: latitude of the waypoint at the beginning of the line (in degrees)
- **longitude1**: longitude of the waypoint at the beginning of the line (in degrees)
- **altitude1**: altitude of the waypoint at the beginning of the line (in m or ft)
- **latitude2**: latitude of the waypoint at the end of the line (in degrees)
- **longitude2**: longitude of the waypoint at the end of the line (in degrees)
- **altitude2**: altitude of the waypoint at the end of the line (in m or ft)
- **straightLine**: 1 if the two points are connected by a straight line, otherwise 0

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```plaintext
GNSSAddWpLine(54.0, 8.0, 0.0, 54.2, 7.9, 0.0, 1);
```
