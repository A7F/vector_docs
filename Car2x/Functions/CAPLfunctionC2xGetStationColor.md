# C2xGetStationColor

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xGetStationColor

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long C2xGetStationColor(long stationHandle);
long C2xGetStationColor(char dbNodeName[]);
```

## Description

Retrieve the color associated with the ITS Station in the Station Manager. The ITS Station can be identified by its handle or by the name of the associated node in the database.

## Parameters

- **stationHandle**: Handle of the ITS station.
- **dbNodeName**: Name of the database node associated with the station.
  - **Note**: CAPL Macro `%NODE_NAME%` can be used as value for the dbNodeName parameter to get the station color for a calling ECU CAPL node.

## Return Values

- **RGB Value (0xBBGGRR)**: The station color encoded as RGB Value (0xBBGGRR).
- **-1**: Error, specified station and/or attribute name do not exist in the scenario.

## Example

```plaintext
on key 'c'
{
  long stationColor;
  stationColor = C2xGetStationColor("%NODE_NAME%");
  write ("Station %NODE_NAME% color : 0x%X", stationColor);
}

void OnC2xPacket (LONG channel, LONG dir, LONG radioChannel, 
LONG signalStrength, LONG sigQuality, LONG packet)
{
  long rxStationHdl;
  long stationColor;

  rxStationHdl = C2xGetStationHandle(packet);
  stationColor = C2xGetStationColor(rxStationHdl);
  stationColor = C2xGetStationColor("DUT");
  stationColor = C2xGetStationColor("%NODE_NAME%");
  write ("Station color: 0x%X", stationColor);
}
```
