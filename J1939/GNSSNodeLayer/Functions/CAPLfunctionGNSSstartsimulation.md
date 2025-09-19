[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSstartsimulation.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSStartSimulation**

# GNSSStartSimulation

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSStartSimulation( dword simType )
```

## Description

This function starts the simulation. At least one waypoint must be set for a start to be successful.

Simulation modes:

- **kWaypoint**: Waypoints that are set are traversed sequentially at the speed from [GNSSSetSpeed](CAPLfunctionGNSSsetspeed.md). If a waypoint is reached to which a speed is assigned, the speed will be accepted by the GNSS receiver.
- **kCourse**: The first waypoint is taken as the starting point; no others are taken into consideration. The GNSS receiver moves at the course derived from [GNSSSetCourse](CAPLfunctionGNSSsetcourse.md) and at the speed from [GNSSSetSpeed](CAPLfunctionGNSSsetspeed.md). When a waypoint is reached to which a speed is assigned, the speed is accepted by the GNSS receiver.
- **kFile**: This mode is used exclusively to play back a position file that was loaded with [GNSSAddWpFile](CAPLfunctionGNSSaddwpfile.md) and the `kUseTime=1` parameter. The speed of the receiver is controlled exclusively by the file.

## Parameters

- **simType**: simulation mode
  - kWaypoint: 0
  - kCourse: 1
  - kFile: 2

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
if ( GNSSStartSimulation(0) == 0 ) {
  write("Start simulation");
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
