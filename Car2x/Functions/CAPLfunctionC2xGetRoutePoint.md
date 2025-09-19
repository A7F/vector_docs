# C2xGetRoutePoint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long C2xGetRoutePoint(char* routeName, int index, out float latitude, out float longitude, out float heading)
```

## Description

Retrieve the latitude, longitude and heading value of the point with given index of route.

## Parameters

- **routeName**: Name of the route
- **index**: Index of the point
- **latitude**: The latitude value of the point as float value.
- **longitude**: The longitude value of the point as float value.
- **heading**: The heading value of the point as float value.

## Return Values

- **0**: Success
- **≠0**: Route not available or failure

## Example

```c
void printRoutePoints(char routeName[])
{
  int i, n;
  float lat, lng, heading;
  n = C2xGetNumberOfRoutePoints(routeName);
  for (i = 1; i < n; i++)
  {
    C2xGetRoutePoint(routeName, i, lat, lng, heading);
    write("Point %i: %f, %f", i, lat, lng);
  }
}
```
