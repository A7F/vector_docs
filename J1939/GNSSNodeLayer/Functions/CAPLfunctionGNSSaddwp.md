[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSaddwp.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSAddWp

# GNSSAddWp

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSAddWp( double latitude, double longitude, double altitude )
```

## Description

This function inserts a new waypoint at the end of the waypoint list. The unit of the altitude parameter depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

- **latitude**: latitude of the new waypoint in degrees
- **longitude**: longitude of the new waypoint in degrees
- **altitude**: altitude of the new waypoint (in m or ft)

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```plaintext
GNSSAddWp( 48.46, 9.11, 225.0 );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
