# C2xGetNodeName

[CAPL Functions](../../CAPLfunctions.md) » Car2x » C2xGetNodeName

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long C2xGetNodeName(long stationHandle, long length, char name[]);
```

## Description

Get the name of the database node which is assigned to the ITS Station in the [StationManager](../../../CANoeCANalyzer/Car2x/windows/StationManager/StationManager.md).

## Parameters

- **stationHandle**: Handle of the ITS station.
- **length**: Maximum number of bytes to be copied.
- **name**: Buffer in which the name is copied. In case no database node is assigned to the ITS station the returned string is empty.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
char   nodeName[1024];
long   stationHdl ;

stationHdl = C2xGetStationHandle(packet) ;
if (C2xGetNodeName(stationHdl, elcount(nodeName), nodeName) == 0)
{
  if (nodeName[0] != 0)
  {
    write("Node: %s", nodeName) ;
  }
  else
  {
    write("Node: no database node assigned") ;
  }
}
```

**See Also**: [C2xGetNodeName](#aanchor21077)
