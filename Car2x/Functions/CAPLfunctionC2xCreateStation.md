[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xCreateStation.md)

**CAPL Functions** » **Car2x** » **C2xCreateStation**

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

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)