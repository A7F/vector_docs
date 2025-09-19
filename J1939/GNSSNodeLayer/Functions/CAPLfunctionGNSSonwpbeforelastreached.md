[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSonwpbeforelastreached.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSOnWpBeforeLastReached**

# GNSSOnWpBeforeLastReached

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void GNSSOnWpBeforeLastReached();
```

## Description

This function is called when the next-to-last waypoint of the waypoint list has been reached. This makes it possible to insert an additional waypoint before the GNSS receiver comes to a stop.

## Parameters

—

## Return Values

—

## Example

```plaintext
// Implementation of a loop
void GNSSOnWpBeforeLastReached()
{
  GNSSAddWpRel( 20.0, 0.0, 0.0 );
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
