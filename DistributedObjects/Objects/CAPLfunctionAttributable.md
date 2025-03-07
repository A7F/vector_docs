[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Objects/CAPLfunctionAttributable.md)

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » attributable

# attributable

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

attributable

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

—

## Description

The type of objects that can have attributes. This type is a supertype of distObjRef *, distObjMemberRef *, distObjInterface *, distObjInterfaceMember *, and virtNet.

The type is not available for user declarations.

## Parameters

—

## Selectors

—

## Example

```plaintext
// vCDL
version 1.4;
namespace ExampleNamespace
{
  interface ExampleInterface
  {
    internal data int32 ExampleMember;
  }
  ExampleInterface ExampleObject;
  attribute int32 ExampleIntAttr { mutable; }
  attribute string ExampleStringAttr { mutable; }
}

// CAPL
on start
{
  dword val;

  // use setAttribute function to set the value of an attribute at an object
  setAttribute(ExampleInterface, ExampleNamespace::ExampleStringAttr, "test");
  setAttribute(ExampleInterface.ExampleMember, ExampleNamespace::ExampleIntAttr, 42);
  setAttribute(ExampleObject, ExampleNamespace::ExampleStringAttr, "test");
  setAttribute(ExampleObject.ExampleMember, ExampleNamespace::ExampleIntAttr, 42);

  // use getAttribute function to read the value of an attribute
  getAttribute(ExampleObject.ExampleMember, _SystemAttributes::AutoSubscribe, val);
  write("AutoSubscribe: %d", val);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)