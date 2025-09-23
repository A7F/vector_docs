[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSScontinuespeed.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSContinueSpeed**

# GNSSContinueSpeed

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSContinueSpeed();
```

## Description

If the speed of the simulation was temporarily reset with the [GNSSPauseSpeed](CAPLfunctionGNSSpausespeed.md) function (set to zero), this function now restores the old speed.

## Parameters

—

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```plaintext
GNSSContinueSpeed();
```
