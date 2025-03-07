[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjInterfaceCreateObjectBlueprint.md)

**CAPL Functions** » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjInterface::CreateObjectBlueprint

# distObjInterface::CreateObjectBlueprint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

[distObjBlueprint](../Objects/CAPLfunctiondistObjBlueprint.md) <Interface> [distObjInterface](../Objects/CAPLfunctiondistObjInterface.md) <Interface>::CreateObjectBlueprint();

[distObjBlueprint](../Objects/CAPLfunctiondistObjBlueprint.md) <Interface> [distObjInterface](../Objects/CAPLfunctiondistObjInterface.md) <Interface>::CreateObjectBlueprint(distObjRef <Interface> object);

## Description

Creates a blueprint for the given interface.

## Parameters

- **object**: Object from which to copy attributes and virtual networks.

## Return Values

- New object blueprint.
- Invalid object blueprint if an error occurred.

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {}
  object Obj : SomeInterface {}
}

// CAPL
on key 'a' {
  distObjBlueprint SomeInterface bp;

  bp = SomeInterface.CreateObjectBlueprint();
  bp = SomeInterface.CreateObjectBlueprint(Obj);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)