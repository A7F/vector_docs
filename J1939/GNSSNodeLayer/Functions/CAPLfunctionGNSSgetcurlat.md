[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSgetcurlat.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSGetCurLat**

# GNSSGetCurLat

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double GNSSGetCurLat();
```

## Description

The function returns the current latitude at which the receiver is located. If a value of 0.0 is returned, the [GNSSGetLastError](CAPLfunctionGNSSgetlasterror.md) function must be used to check whether the value is valid (see [error codes](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)).

## Parameters

—

## Return Values

current latitude (in degrees)

## Example

```plaintext
double lat;
lat = GNSSGetCurLat();

if (lat == 0 && GNSSGetLastError() != 0 ) {
  write("Error: Invalid current latitude");
}
```
