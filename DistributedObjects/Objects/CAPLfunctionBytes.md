[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Objects/CAPLfunctionBytes.md)

**CAPL Functions** » [Distributed Objects](../CAPLfunctionsDOOverview.md) » bytes

# bytes

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`bytes`

## Method Syntax

—

## Description

The corresponding CAPL type for the bytes type in [vCDL](../../../vCDL/Language/vCDLBytesDataTypes.md). Reading and writing is done via [memcpy](../../StructByteAccess/Functions/CAPLfunctionMemCpy.md) overloads. The length of a bytes value can be determined with the **elCount** operator.

This type is not available for user declarations.

## Parameters

—

## Selectors

—

## Example

```c
// vCDL
version 1.4;
namespace ExampleNamespace
{
  object ExampleObject
  {
    internal data bytes ExampleMember;
  }
}

// CAPL
on start
{
  byte buffer[100];

  // write whole buffer to bytes value
  memcpy($ExampleNamespace::ExampleObject.ExampleMember, buffer);
  // write part of buffer to bytes value
  memcpy($ExampleNamespace::ExampleObject.ExampleMember, buffer, 42);
  // read from bytes value
  memcpy(buffer, $ExampleNamespace::ExampleObject.ExampleMember);
  write("Length: %d", elCount($ExampleNamespace::ExampleObject.ExampleMember));
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)