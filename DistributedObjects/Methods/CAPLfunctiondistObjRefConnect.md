[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjRefConnect.md)

# distObjRef::Connect

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjRef::Connect

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

void [distObjRef](../Objects/CAPLfunctiondistObjRef.md)::Connect();

## Description

This is a collective operation that connects every member of the object with its virtual network.

## Parameters

—

## Return Values

—

## Example

```plaintext
on start
{
  distObjRef * object = ExampleObject;
  object.Connect();
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)