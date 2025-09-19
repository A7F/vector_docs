[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSappcmdaddrindication.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSAppCmdAddrIndication**

# GNSSAppCmdAddrIndication

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void GNSSAppCmdAddrIndication( long newAddress )
```

## Description

This function indicates that a new address has been assigned to the node by the "Commanded Address" parameter group. The node must log on to the bus again with the assigned address (see [GNSSStartUp](CAPLfunctionGNSSstartup.md)).

## Parameters

- **newAddress**: New address of the node

## Return Values

—

## Example

```plaintext
void GNSSAppCmdAddrIndication( LONG newAddr )
{
  GNSSShutDown();
  GNSSStartUp( gName, newAddr );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
