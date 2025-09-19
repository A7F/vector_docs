[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSsetpgsettings.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSSetPGSettings

# GNSSSetPGSettings

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSSetPGSettings( dword pgn, dword enable, dword destination, dword priority, dword updateRate )
```

## Description

This function can be used to change the values of individual parameter groups. Supported parameter groups include:

- "GNSS Position Data" (PGN 129029)
- "Position Delta, High Precision Rapid Update" (PGN 129027)
- "Position, Rapid Update" (PGN 129025)
- "COG & SOG, Rapid Update" (PGN 129026)
- "VehiclePosition" (PGN 65267)
- "Vehicle Direction/Speed" (PGN 65256)

By default, "Vehicle Direction/Speed" is not transmitted cyclically. If enabled, this message can be requested by a request message.

When a node is reached with [GNSSStartUp](CAPLfunctionGNSSstartup.md), the following start values are set:

- **pgn**: 129029, **enable**: 1, **destination**: 255, **priority**: 3, **updateRate**: 1000
- **pgn**: 129027, **enable**: 0, **destination**: 255, **priority**: 2, **updateRate**: 100
- **pgn**: 129025, **enable**: 1, **destination**: 255, **priority**: 2, **updateRate**: 100
- **pgn**: 129026, **enable**: 0, **destination**: 255, **priority**: 2, **updateRate**: 250
- **pgn**: 65267, **enable**: 0, **destination**: 255, **priority**: 6, **updateRate**: 1000
- **pgn**: 65256, **enable**: 0, **destination**: 255, **priority**: 6, **updateRate**: 0

The function is only performed successfully if the simulation has not yet been started.

## Parameters

- **pgn**: number of the parameter group
- **enable**: 1 if this parameter group should be sent, otherwise 0
- **destination**: target address of the parameter group
- **priority**: priority of the parameter group
- **updateRate**: time interval in milliseconds at which the parameter group is sent

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
// disable PG "Position, Rapid Update"
GNSSSetPGSettings( 129025, 0, 255, 3, 1000 );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
