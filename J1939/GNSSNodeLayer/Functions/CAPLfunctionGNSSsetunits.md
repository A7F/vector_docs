[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSsetunits.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSSetUnits**

# GNSSSetUnits

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSSetUnits( dword unitType )
```

## Description

This function determines the system of units of measure that will be used by the various other functions.

Units of measure:

- **kMetricSystem**: Meters (m), kilometers (km), kilometers/hour (km/h)
- **kEnglishSystem**: Yards (yd), miles (mi), miles/hour (mph)
- **kNauticSystem**: Yards (yd), nautical miles (nmi), knots (kn)

When the node is set up, the metric system for [units of measures](../../../../CANoeCANalyzer/J1939/gnssNL/gnssNLUnits.md) is set.

## Parameters

- **unitType**: units of measure
  - 0: kMetricSystem
  - 1: kEnglishSystem
  - 2: kNauticSystem

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
// set nautic system
GNSSSetUnits( 2 );
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
