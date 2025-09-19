# C2xMoveRouteRelativeToRefPoint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `C2xMoveRouteRelativeToRefPoint(char* routeName, char* refRouteName, char* refPointName)` //form 1
- `C2xMoveRouteRelativeToRefPoint (char* routeName, char* refRouteName, int refPointID)` //form 2
- `C2xMoveRouteRelativeToRefPoint(char* routeName, char* refRouteName, char* refPointName, char* stationName)` //form 3
- `C2xMoveRouteRelativeToRefPoint (char* routeName, char* refRouteName, int refPointID, char* stationName)` //form 4

## Description

If the current scenario is running, it must be stopped via [C2xStopScenario()](CAPLfunctionC2xStopScenario.md) function call or by stopping scenario in Scenario Manager window.

### Form 1 and 2:

This function sets the reference point defined by `refPointName` on the route specified by `refRouteName`. The position is determined by the starting point of the route and the offset of the reference point. The route defined by `routeName` is translated and rotated such that it is located relative to the reference point in the same angle and distance as in the original scenario.

### Form 3 and 4:

This function sets the reference point defined by `refPointName` on the route specified by `refRouteName`. The position is determined by the starting point of the route and the offset of the reference point. The route defined by `routeName` is then transformed such that it intersects with the reference point in the same angle and distance as in the original scenario. Only the station specified by `stationName` is taken into account on the route. All other stations located on the route keep their original trajectory.

## Parameters

- **routeName**: Name of the route that should be moved
- **refRouteName**: Name of the route where the scenario reference point should be set on
- **refPointName (form 1,3)**: Name of the scenario reference point
- **refPointID (form 2,4)**: ID of the scenario reference point
- **stationName**: Name of the station

## Return Values

- **1**: Success
- **-1**: Specified route(s), reference point and/or station do not exist in the scenario
- **-2**: Route cannot be moved because current scenario is still running
- **-3**: The reference point cannot be set on the route specified by refRouteName, as the route is too short

## Example

```plaintext
on key 's'
{
  C2xLoadRoute("MyRouteFile.kml", "MyCustomRoute",0);

  C2xSetStationsOnRoute("DuT_Route","MyCustomRoute");
  C2xSetRouteStartPoint("MyCustomRoute", "DuT", @GNSS::Ath1.Latitude, @GNSS::Ath1.Longitude, @GNSS::Ath1.Direction);
  C2xMoveRouteRelativeToRefPoint("EVA_Route", "MyCustomRoute", "CollisionPoint1", "Sender_EVA");

  C2xStartScenario();
}
```
