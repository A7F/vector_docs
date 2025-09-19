[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSonsetspeed.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSOnSetSpeed**

# GNSSOnSetSpeed

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void GNSSOnSetSpeed( double speed )
```

## Description

This function is called if the speed of the simulation has been changed. This is helpful in the case of simulation by a file when the speed is determined from the file (see [GNSSStartSimulation](CAPLfunctionGNSSstartsimulation.md)).

The unit of the parameter depends on the system of measurement units selected with the [GNSSSetUnits](CAPLfunctionGNSSsetunits.md) function.

## Parameters

- **speed**: New speed (in km/h, mph or kn)

## Return Values

—

## Example

```plaintext
void GNSSOnSetSpeed( double speed )
{
  write("New speed = %lf", speed )
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
