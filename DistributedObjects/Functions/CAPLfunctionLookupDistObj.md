[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Functions/CAPLfunctionLookupDistObj.md)

**CAPL Functions** » **Distributed Objects** » **lookupDistObj**

# lookupDistObj

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
distObjRef * lookupDistObj(char path[]);
```

## Description

Obtains an object by using a string. A downcast can be used to get a more concrete type.

## Parameters

- **path**: Fully qualified name of the object.

## Return Values

- Object with the given path.
- Invalid object if nothing was found.

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {
    internal data int32 d;
  }
  object Obj : SomeInterface {}
}

// CAPL
on key 'a' {
  distObjRef SomeInterface x;

  // downcast with typename
  x = (distObjRef SomeInterface)lookupDistObj("SomeNamespace::Obj");

  // downcast with __type_of
  x = (__type_of(x))lookupDistObj("SomeNamespace::Obj");
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)