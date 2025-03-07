[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSgetcurcourse.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSGetCurCourse**

# GNSSGetCurCourse

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
double GNSSGetCurCourse( void )
```

## Description

This function returns the current course in degrees along which the GNSS receiver is moving.

If a value of 0.0 is returned, the [GNSSGetLastError](CAPLfunctionGNSSgetlasterror.md) function must be used to check whether the value is valid (see [error codes](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)).

## Parameters

—

## Return Values

current course in degrees

## Example

```plaintext
double course;
course = GNSSGetCurCourse();
write("Course = %lf degree", course);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)