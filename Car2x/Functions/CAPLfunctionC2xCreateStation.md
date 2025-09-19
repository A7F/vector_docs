# C2xCreateStation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
Int64 C2xCreateStation(char* stationName);
```

## Description

Creates a station and assigns it to the currently loaded scenario. If no scenario is loaded, a temporary scenario is created after measurement is started.

## Parameters

- **stationName**: Name of the station. The name must match the name of the node in the database.

## Return Values

- **0**: OK
- **-1**: Error

## Example

```c
on start
{
  C2xCreateStation("Station1");
}
```

