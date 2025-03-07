# C2xGetStationName

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetStationName.md)

**CAPL Functions** » Car2x » C2xGetStationName

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long C2xGetStationName(long stationHandle, long length, char name[]);
```

## Description

Get the name assigned to the ITS Station in the [StationManager](../../../CANoeCANalyzer/Car2x/windows/StationManager/StationManager.md).

## Parameters

- **stationHandle**: Handle of the ITS station.
- **length**: Maximum number of bytes to be copied.
- **name**: Buffer in which the name is copied.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```c
char   stationName[1024];
long   stationHdl ;

stationHdl = C2xGetStationHandle(packet) ;
if (C2xGetStationName(stationHdl, elcount(stationName), stationName) == 0)
{
  write("Station: %s", stationName) ;
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)