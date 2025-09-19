[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSaddwpfile.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSAddWpFile**

# GNSSAddWpFile

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSAddWpFile( byte filepath[], dword useTimeInfo )
```

## Description

The function deletes all waypoints in the waypoint list and then inserts the GNSS positions of a file into the list.

- **useTimeInfo = 0**: The waypoints are inserted without speed information (according to the [GNSSAddWp](CAPLfunctionGNSSaddwp.md) function). The speed of the receiver is controlled by [GNSSSetSpeed](CAPLfunctionGNSSsetspeed.md). The value **kWaypoint** must be used as a simulation mode in [GNSSStartSimulation](CAPLfunctionGNSSstartsimulation.md).

- **useTimeInfo = 1**: The speed is controlled by the file. Only GNSS positions from the file are used to which a time > 0 is assigned. The speed is calculated by means of the difference in time and space between two successive positions. The value **kFile** must be used as a simulation mode in [GNSSStartSimulation](CAPLfunctionGNSSstartsimulation.md).

## Parameters

- **filepath**: path of the file with position information
- **useTimeInfo**:
  - 0: if the position information is used only
  - 1: if position and time information are used

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
char filePath[255] = "C:\\log.pos";
GNSSAddWpFile(filePath, 1);
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
