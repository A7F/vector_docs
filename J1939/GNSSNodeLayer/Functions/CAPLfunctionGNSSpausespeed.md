[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSpausespeed.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSPauseSpeed**

# GNSSPauseSpeed

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSPauseSpeed();
```

## Description

This function temporarily sets the speed to zero. The GNSS receiver thus remains in place where it is, but continues to send position data. This also applies to playing back a position file.

You can use the [GNSSContinueSpeed](CAPLfunctionGNSScontinuespeed.md) function to accept the old speed again.

## Parameters

—

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
