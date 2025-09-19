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
