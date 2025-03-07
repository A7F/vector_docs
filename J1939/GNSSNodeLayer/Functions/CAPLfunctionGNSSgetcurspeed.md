[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSgetcurspeed.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSGetCurSpeed**

# GNSSGetCurSpeed

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double GNSSGetCurSpeed();
```

## Description

This function returns the current speed at which the GNSS receiver is moving. If a value of 0.0 is returned, the [GNSSGetLastError](CAPLfunctionGNSSgetlasterror.md) function must be used to check whether the value is valid.

The unit of the parameter depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

—

## Return Values

- Current speed (in km/h, mph or kn)

## Example

```plaintext
double speed;
GNSSSetUnits( 0 );
speed = GNSSGetCurSpeed();
write("Speed = %lf km/h", speed);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)