[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSgetcurlon.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSGetCurLon

# GNSSGetCurLon

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double GNSSGetCurLon();
```

## Description

The function returns the current longitude at which the receiver is located. If a value of 0.0 is returned, the [GNSSGetLastError](CAPLfunctionGNSSgetlasterror.md) function must be used to check whether the value is valid (see [error codes](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)).

## Parameters

—

## Return Values

current longitude (in degrees)

## Example

```plaintext
double lon;
lon = GNSSGetCurLon();

if (lon == 0 && GNSSGetLastError() != 0 ) {
  write("Error: Invalid current longitude");
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
