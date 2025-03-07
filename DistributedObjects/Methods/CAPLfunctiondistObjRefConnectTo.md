[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjRefConnectTo.md)

# distObjRef::ConnectTo

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjRef::ConnectTo

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
void distObjRef::ConnectTo(virtNet network);
```

## Description

This is a collective operation that connects every member of the object, if it is assigned to the given virtual network.

## Parameters

- **network**: Virtual network to connect to.

## Return Values

—

## Example

```plaintext
on start
{
  distObjRef * object = ExampleObject;
  object.ConnectTo(virtNet::Default);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)