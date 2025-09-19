# C2xStartScenario

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xStartScenario.md)

**CAPL Functions** » **Car2x** » C2xStartScenario

**Valid for**: CANoe DE

## Function Syntax

- `long C2xStartScenario(); // form 1`
- `long C2xStartScenario(char* stationName, double latitude, double longitude, double heading); // form 2`

## Description

**Form 1**

This function starts the scenario assigned to the current CANoe DE product configuration immediately. The scenario can also be started manually in Scenario Manager Window. In both cases, the successful scenario start will be indicated by [OnScenarioStart()](../Callbacks/CAPLfunctionC2xOnStartScenario.md) callback function.

**Form 2**

Starts the current scenario at specified geographical position (latitude, longitude) in specified direction (heading parameter). The original scenario will be transformed in the following way before the scenario starts:

1. All routes and stations in the scenario will be moved to a new geographical position in a way that the position of the scenario station specified by `stationName` parameter is equal to geographical position specified in `latitude` and `longitude` parameters.
2. All routes and stations in the scenario will be rotated around the geographical position specified in `latitude` and `longitude` parameters until the route of the scenario station specified by `stationName` have the same direction as specified in the `heading` parameter.

Original scenario data transformations (moving and rotating) done by this function are active until the scenario stop.

## Parameters

- **stationName (form 2)**: Name of the scenario station.
- **latitude (form 2)**: Actual geographical latitude of the station.
- **longitude (form 2)**: Actual geographical longitude of the station.
- **heading (form 2)**: Actual heading of the station relative to the north.

## Return Values

- **1**: Success
- **-1**: Error, scenario start was not successful.
- **-2**: Error, invalid or out of range parameter specified.

## Example

**Example for Form 1**

```plaintext
on key 'r'
{
  if (C2xStartScenario() == 1)
  {
    write("Scenario started");
  }
}

on key 's'
{
  if (C2xStopScenario() == 1)
  {
    write("Scenario stopped");
  }
}

void OnStartScenario()
{
  write("%f sec - OnStartScenario was called" , TimeNowNS()/1e9);
}
```

**Example for Form 2**

```plaintext
Form 2:
on key 's'
{
  double lat = 48.8234237480101;
  double lon = 9.09433094246674;
  double heading = 45.0;
  if (C2xStartScenario("MyStation", lat, lon, heading) == 1)
  {
    write("Scenario started");
  }
}
```
