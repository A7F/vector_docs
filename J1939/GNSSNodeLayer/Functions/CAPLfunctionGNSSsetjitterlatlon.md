[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSsetjitterlatlon.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSSetJitterLatLon

# GNSSSetJitterLatLon

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSSetJitterLatLon( double  jitter )
```

## Description

This function sets the jitter by which the longitudinal and latitudinal degree deviates from the respective nominal value. The unit of the parameter depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

- **jitter**: magnitude of the jitter (in m or yd)

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
double jitter = 1.5;
GNSSSetUnits( 0 );
GNSSSetJitterLatLon( jitter ); // 1.5 m
```
