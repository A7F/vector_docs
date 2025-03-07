[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionSetStationSpeed.md)

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » SetStationSpeed

# SetStationSpeed

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
Int64 SetStationSpeed(char* stationName, double speed, double acceleration);
```

## Description

With this function, the speed of a station can be changed. The parameter speed defines the speed that has to be reached with a given acceleration (2nd parameter).

**Note**: This function does not work for dynamically added stations because their speed is defined by the frequency their positions are provided.

## Parameters

- **stationName**: Name of the station. The name must match the name of the node in the database.
- **speed**: The new speed of the station in km/h.
- **acceleration**: The used acceleration in m/s² to reach the new speed (in case of deceleration, this will be calculated automatically).

## Return Values

- **0**: OK
- **-1**: Error

## Example

```plaintext
on start
{
  SetStationSpeed("Station1", 200.0, 15.0);
}
```

[See Also](#aanchor28451)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)