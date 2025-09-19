# distObjContainerRef::Create

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

- `long distObjContainerRef <Typedef name>::Create(dword index);`
- `long distObjContainerRef <Typedef name>::Create(dword index, distObjBlueprint <Interface> blueprint);`

## Description

Creates a new object at the given index. It requires that **<Typedef name>** refers to an object array type.

## Parameters

- **index**: Index at which to create the object.
- **blueprint**: Blueprint which is used for object creation.

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
  array<SomeInterface, 42> ObjList;
}

// CAPL
on key 'a' {
  // first remove an object
  ObjList.Erase(2);

  // then create one
  ObjList.Create(2);
}
```
