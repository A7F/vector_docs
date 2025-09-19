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
