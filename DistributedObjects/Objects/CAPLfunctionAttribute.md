[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Objects/CAPLfunctionAttribute.md)

# attribute

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » attribute

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `attribute *`
- `attribute int32`
- `attribute uint32`
- `attribute int64`
- `attribute uint64`
- `attribute double`
- `attribute string`

## Method Syntax

—

## Description

The types of attributes for distributed objects. These types are not available for user declarations.

## Parameters

- **int32**: 32-Bit signed integer attribute. Access requires type long in CAPL.
- **uint32**: 32-Bit unsigned integer attribute. Access requires type dword in CAPL.
- **int64**: 64-Bit signed integer attribute. Access requires type int64 in CAPL.
- **uint64**: 64-Bit unsigned integer attribute. Access requires type qword in CAPL.
- **double**: 64-Bit floating point attribute. Access requires type double in CAPL.
- **string**: String attribute. Access requires a large enough char array in CAPL.

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

  // reference attributes in CAPL
  ExampleNamespace::ExampleIntAttr;
  ExampleNamespace::ExampleStringAttr;

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