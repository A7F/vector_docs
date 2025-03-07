[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Objects/CAPLfunctionvirtNet.md)

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » virtNet

# virtNet

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

virtNet

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

—

## Description

References a virtual network.

## Parameters

—

## Selectors

- **Name**
  - Type: `char[]`
  - Access Limitation: Read only
  - Description: Name of the object.
  
- **Path**
  - Type: `char[]`
  - Access Limitation: Read only
  - Description: Path of the object.

## Example

```plaintext
on start
{
  DistObjRef * object = SomeObject;
  object.ConnectTo(virtNet::Default);
  write("Connecting to: %s", virtNet::Default.Path);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)