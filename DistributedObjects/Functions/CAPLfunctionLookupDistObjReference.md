[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Functions/CAPLfunctionLookupDistObjReference.md)

**CAPL Functions** » **Distributed Objects** » **lookupDistObjReference**

# lookupDistObjReference

Valid for: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
distObjReferenceRef * lookupDistObjReference(char path[]);
```

## Description

Obtains a reference by using a string. A downcast can be used to get a more concrete type.

## Parameters

- **path**: Fully qualified name of the reference.

## Return Values

- Reference with the given path.
- Invalid reference if nothing was found.

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
    interface SomeInterface {
        internal data int32 d;
    }
    reference<SomeInterface> Ref;
}

// CAPL
on key 'a' {
    distObjReferenceRef SomeInterface x;

    // downcast with typename
    x = (distObjReferenceRef SomeInterface)lookupDistObjReference("SomeNamespace::Ref");

    // downcast with __type_of
    x = (__type_of(x))lookupDistObjReference("SomeNamespace::Ref");
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)