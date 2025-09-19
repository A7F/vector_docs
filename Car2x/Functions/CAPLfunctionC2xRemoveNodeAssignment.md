# C2xRemoveNodeAssignment

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xRemoveNodeAssignment(long stationHandle);
```

## Description

Removes an assigned database node from an ITS station.

## Parameters

- **stationHandle**: The station handle for which the node assignment should be removed.

## Return Values

- **0**: OK
- **-1**: Internal error
- **1**: No station found for parameter stationHandle
- **2**: No error but station had no node assigned to remove

## Example

```plaintext
on key 'c'
{
    long stationHdl;

    stationHdl = C2xGetStationHandle("Car1");
    C2xRemoveNodeAssignment(stationHdl);
}
```
