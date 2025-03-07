[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjRefDisconnectFrom.md)

# distObjRef::DisconnectFrom

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjRef::DisconnectFrom

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
void distObjRef::DisconnectFrom(virtNet network);
```

## Description

This is a collective operation that disconnects every member of the object, if it is assigned to the given virtual network.

## Parameters

- **network**: Virtual network to disconnect from.

## Return Values

—

## Example

```plaintext
on start
{
  distObjRef * object = ExampleObject;
  object.DisconnectFrom(virtNet::Default);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)