# C2xSetStationOnRoute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long C2xSetStationOnRoute(char* stationName, char* targetRouteName*)
```

## Description

If the current scenario is running, it must be stopped via [C2xStopScenario()](CAPLfunctionC2xStopScenario.md) function call or by stopping scenario in Scenario Manager window.

This function sets the station specified by **stationName** on the route specified by **targetRouteName**.

## Parameters

- **stationName**: Name of the specific station that should be set on targetRouteName
- **targetRouteName**: Name of the route that the station should be set on

## Return Values

- **1**: Success
- **-1**: Routes and/or station do not exist in the loaded scenario.
- **-2**: Station cannot be set on the given route, because current scenario is still running
- **-3**: Station cannot be set on the given route, because the offset of the station is larger than the route length

## Example

```c
on key 's'
{
  double lat = 48.8234237480101;
  double lon = 9.09433094246674;
  double heading = 45.0;
  C2xLoadRoute("/Routes/MyRouteFile.kml", "MyCustomRoute",0);
  C2xSetStationOnRoute("DuT","MyCustomRoute");
  C2xSetRouteStartPoint("MyCustomRoute", "DuT", lat, lon, heading);
  C2xStartScenario();
}
```
