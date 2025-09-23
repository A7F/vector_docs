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
