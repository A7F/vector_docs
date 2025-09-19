[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSetRouteStartPoint.md)

## C2xSetRouteStartPoint

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xSetRouteStartPoint

**Valid for**: CANoe DE

### Function Syntax

- `long C2xSetRouteStartPoint(char* routeName, double latitude, double longitude, double heading)` // form 1
- `long C2xSetRouteStartPoint(char* routeName, char* stationName, double latitude, double longitude, double heading)` // form 2

### Description

If the current scenario is running, it must be stopped via [C2xStopScenario()](CAPLfunctionC2xStopScenario.md) function call or by stopping scenario in Scenario Manager window.

#### Form 1

All stations positioned on the route specified by **routeName** are moved such that the position of **StartOffset** = 0 is located at the projection of the geographical position given in latitude and longitude parameters on the route. The following condition must be met:

1. There is a part of the route which direction does not differ more than 90 degrees from the direction specified in the **heading** parameter.

#### Form 2

All stations positioned on the route specified by **routeName** are moved such that the station specified by **stationName** is located at the projection of the geographical position given in latitude and longitude parameters on the route. The following conditions must be met:

1. The station specified by **stationName** is located on the route specified by **routeName**.
2. There is a part of the route which direction does not differ more than 90 degrees from the direction specified in the **heading** parameter.

**Note:** The position in latitude and longitude should have a reasonable distance to the specified route.

### Parameters

- **routeName**: Name of the route
- **stationName (form 2)**: Name of the scenario station
- **latitude**: Actual geographical latitude of the station
- **longitude**: Actual geographical longitude of the station
- **heading**: Actual geographical heading of the station

### Return Values

- **1**: Success
- **-1**: Specified route and/or station name do not exist in the scenario.
- **-2**: Station(s) cannot be moved because current scenario is still running.
- **-3**: Start point of route cannot be changed, because the given position is too far away or the offset of the station(s) is larger than the remaining route length.

### Example

```plaintext
on key 's'
{
  double lat = 48.8234237480101;
  double lon = 9.09433094246674;
  double heading = 45.0;
  C2xLoadRoute("MyRouteFile.kml", "MyCustomRoute",0);
  C2xSetStationsOnRoute("ScenarioDefinitionRoute","MyCustomRoute");
  C2xSetRouteStartPoint("MyCustomRoute", "DuT", lat, lon, heading);
  C2xStartScenario();
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
