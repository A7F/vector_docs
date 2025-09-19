# C2xSetStationsOnRoute

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

`long C2xSetStationsOnRoute(char* sourceRouteName, char* targetRouteName)`

## Description

If the current scenario is running, it must be stopped via [C2xStopScenario()](CAPLfunctionC2xStopScenario.md) function call or by stopping scenario in Scenario Manager window.

This function sets all stations currently positioned on the route specified by `sourceRouteName` on the route specified by `targetRouteName`.

## Parameters

- **sourceRouteName**: Name of the route that stations should be moved from
- **targetRouteName**: Name of the route that stations should be set on

## Return Values

- **1**: Success
- **-1**: Route(s) and/or station do not exist in the loaded scenario.
- **-2**: Station(s) cannot be set on the given route, because current scenario is still running
- **-3**: Station(s) cannot be set on the given route, because the offset of the station(s) is larger than the route length

## Example

```plaintext
on key 's'
{
  double lat = 48.8234237480101;
  double lon = 9.09433094246674;
  double heading = 45.0;
  C2xLoadRoute("/Routes/MyRouteFile.kml", "MyCustomRoute",0);
  C2xSetStationsOnRoute("ScenarioDefinitionRoute","MyCustomRoute");
  C2xSetRouteStartPoint("MyCustomRoute", "DuT", lat, lon, heading);
  C2xStartScenario();
}
```
