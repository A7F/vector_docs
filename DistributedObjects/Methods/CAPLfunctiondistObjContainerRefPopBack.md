# distObjContainerRef::PopBack

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
long distObjContainerRef <Typedef name>::PopBack();
```

## Description

Removes an element at the end of the container.

It requires that **<Typedef name>** refers to a list type.

## Parameters

—

## Return Values

- **0**: OK
- **1**: An error occurred

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {
    internal data int32 d;
  }
  object Obj : SomeInterface {}
  list<SomeInterface> ObjList;
  list<reference<SomeInterface>> RefList;
}

// CAPL
on key 'a' {
  // initialize with 42 elements
  ObjList.Length = 42;
  RefList.Length = 42;

  // remove the last element
  ObjList.PopBack();
  RefList.PopBack();
}
```
