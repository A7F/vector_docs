[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSsetspeed.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSSetSpeed**

# GNSSSetSpeed

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSSetSpeed( double  speed )
```

## Description

This function sets the speed at which the GNSS receiver moves. The unit of the parameter depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

- **speed**: speed of the simulation (in km/h, mph or kn)

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
GNSSSetUnits( 2 );  // set nautic system
GNSSSetSpeed( 20 ); // new speed: 20 Knots
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
