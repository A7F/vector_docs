[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xAdjustStationSpeedForCollision.md)

## CAPL Functions » Car2x » C2xAdjustStationSpeedForCollision

### C2xAdjustStationSpeedForCollision

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

- `long C2xAdjustStationSpeedForCollision (char* stationName, char* refPointName, double latitude, double longitude, double speed, double offsetToRefPoint)` //form 1
- `long C2xAdjustStationSpeedForCollision (char* stationName, int refPointID, double latitude, double longitude, double speed, double offsetToPoint)` //form 2

### Description

If the current scenario is not running, it must be started via [C2xStartScenario()](CAPLfunctionC2xStartScenario.md) function call or by starting scenario in Scenario Manager window.

This function adjusts the speed of the station specified by **stationName** in relation to a reference station described by its geographical position (**latitude**, **longitude**) and **speed**. The speed of the station specified by **stationName** is adjusted in a way such:

1. The reference station and the station collide at the reference point specified by **refPointName** (form 2: **refPointID**), assuming the speed given in **speed** stays constant.
2. If the offset given in **offsetToRefPoint** differs from zero, the stations will not collide but instead pass the reference point according to the offset.
3. The reference station is defined by its actual geographical position and speed given in latitude, longitude, and speed. The station must be located on the same route as the reference point.

The following conditions must be met:

1. The position given by longitude, latitude must be located on the same route as the reference point.
2. The reference point must be close to the route of the station specified by stationName.

**Note**: In order to adjust the speed to a station with dynamic speed, the function should be called multiple times, e.g. with a timer.

### Parameters

- **stationName**: Name of the scenario station
- **refPointName (form 1)**: Name of the scenario reference point
- **refPointID (form 2)**: ID of the scenario reference point
- **latitude**: Actual geographical latitude of the station approaching the reference point
- **longitude**: Actual geographical longitude of the station approaching the reference point
- **speed**: Actual speed of the station approaching the reference point
- **offsetToRefPoint**: Offset to the point at time of collision

### Return Values

- **1**: Success
- **-1**: Specified station and/or reference point do not exist in the scenario
- **-2**: Adjustment not possible, because scenario is not running or the reference point was already reached

### Example

```plaintext
on timer calculationTimer
{
  if (C2xIsScenarioStarted())
  {
    C2xAdjustStationSpeedForCollision("Sender_EVA", "CollisionPoint1", @GNSS::Ath1.Latitude, @GNSS::Ath1.Longitude, @GNSS::Ath1.Speed, 0);
  }
}
```
