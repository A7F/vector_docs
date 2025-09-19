# C2xLoadRoute

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xLoadRoute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long C2xLoadRoute(char* routeFilePath, char* routeName, int loopFlag)
```

## Description

This function loads the route with the name **routeName** from the file specified by **routeFilePath** parameter and adds it to the currently loaded scenario.

**Note**

- Available file formats are nmea, gpx, and kml.
- The route names in the file depend on the file format:
  - .nmea: name is the same as filename
  - .gpx: name is same as the trk-name given in file
  - .kml: name is same as the Placemark-name given in file

After loading, the route is available for further operations as long as the scenario is loaded, for example to transfer a station on another route.

If specified, the loaded route is configured as a loop and is considered a continuous path.

**Note**

- The configuration as a loop should be physically plausible. This includes the distance between end and start point of the loaded route as well as the heading difference. For example, stations driving on the route cannot change their heading by 90° while driving at high speed etc.

## Parameters

- **routeFilePath**: The path to the route file, e.g., c:\SomeFolder\TestRoute.gpx. The relative file paths are also accepted with relation to CANoe DE product configuration folder.

## Return Values

- **1**: Success
- **-1**: Route loading error or invalid routeFilePath parameter.
- **-2**: Route cannot be loaded as route with the same name already exists.

## Example

```c
void OnScenarioStateChanged(long newState)
{
    if (newState == 0) // new scenario file was loaded
    {
        //C2xLoadRoute("c:\SomeFolder\ MyRouteFile.kml", "MyCustomRoute", 0);
        C2xLoadRoute("MyRouteFile.kml", "MyCustomRoute", 0);
        C2xLoadRoute("MyRouteFile.kml", "MyCustomLoopedRoute", 1);
    }
}
```
