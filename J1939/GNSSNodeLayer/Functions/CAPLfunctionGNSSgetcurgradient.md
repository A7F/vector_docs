[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSgetcurgradient.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSGetCurGradient

# GNSSGetCurGradient

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double GNSSGetCurGradient();
```

## Description

This function returns the current gradient in degrees at which the GNSS receiver is moving.

If a value of 0.0 is returned, the [GNSSGetLastError](CAPLfunctionGNSSgetlasterror.md) function must be used to check whether the value is valid (see [error codes](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)).

## Parameters

—

## Return Values

current gradient in degrees

## Example

```c
double gradient;
gradient = GNSSGetCurGradient();
write("Gradient = %lf degree", gradient);
```
