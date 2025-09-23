[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSgetcuralt.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSGetCurAlt**

# GNSSGetCurAlt

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
double GNSSGetCurAlt();
```

## Description

The function returns the current altitude at which the receiver is located. If a value of 0.0 is returned, the [GNSSGetLastError](CAPLfunctionGNSSgetlasterror.md) function must be used to check whether the value is valid (see [error codes](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)).

The unit of the altitude depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

—

## Return Values

current altitude (in m or ft)

## Example

```plaintext
double alt;
alt = GNSSGetCurAlt();

if (alt == 0 && GNSSGetLastError() != 0 ) {
  write("Error: Invalid current altitude");
}
```
