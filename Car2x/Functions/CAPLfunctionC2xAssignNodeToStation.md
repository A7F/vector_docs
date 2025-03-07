[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xAssignNodeToStation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xAssignNodeToStation

# C2xAssignNodeToStation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xAssignNodeToStation(long stationHandle, char* dbName, chat* nodeName);
```

## Description

Assigns a database node to an ITS station.

## Parameters

- **stationHandle**: Handle of the station to assign the database node to.
- **dbName**: Name of the database
- **nodeName**: Name of the node to assign

## Return Values

- **0**: Ok
- **-1**: Internal error
- **1**: No station found for the parameter stationHandle
- **2**: No dbNode found to assign

## Example

```plaintext
on key 'c'
{
    long stationHdl;

    stationHdl = C2xGetStationHandleByStationName("Car1");

    C2xAssignNodeToStation(stationHdl, "EU_ApplMsg", "Car1");
}
```

[See Also](javascript:void(0);)