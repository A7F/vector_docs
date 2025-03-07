[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Functions/CAPLfunctionLookupDistObjContainer.md)

**CAPL Functions** » [Distributed Objects](../CAPLfunctionsDOOverview.md) » lookupDistObjContainer

# lookupDistObjContainer

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
distObjContainerRef * lookupDistObjContainer(char path[]);
```

## Description

Obtains a container by using a string. A downcast can be used to get a more concrete type.

## Parameters

- **path**: Fully qualified name of the container.

## Return Values

- Container with the given path.
- Invalid container if nothing was found.

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {
    internal data int32 d;
  }
  typedef ContainerType = array<SomeInterface, 42>;
  ContainerType Container;
}

// CAPL
on key 'a' {
  distObjContainerRef SomeNamespace::ContainerType x;

  // downcast with typename
  x = (distObjContainerRef SomeNamespace::ContainerType)lookupDistObjContainer("SomeNamespace::Container");

  // downcast with __type_of
  x = (__type_of(x))lookupDistObjContainer("SomeNamespace::Container");
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)