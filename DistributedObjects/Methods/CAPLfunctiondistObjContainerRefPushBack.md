# distObjContainerRef::PushBack

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjContainerRef::PushBack

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

- `long distObjContainerRef <Typedef name>::PushBack(); // form 1`
- `long distObjContainerRef <Typedef name>::PushBack(char path[]); // form 2`
- `long distObjContainerRef <Typedef name>::PushBack(distObjRef <Interface> target); // form 3`
- `long distObjContainerRef <Typedef name>::PushBack(distObjBlueprint <Interface> blueprint); // form 4`

## Description

Adds an element at the end of the container. It requires that **`<Typedef name>`** refers to a list type.

- The first overload is available for lists of objects and references. It appends a default object or reference.
- Form 2 and 3 are only available when **`<Typedef name>`** refers to a (nested) list of references. Here the parameter can be used to directly set the target of the new reference.
- Form 4 is only available when **`<Typedef name>`** refers to a (nested) list of objects.

## Parameters

- **path**: Fully qualified name of the target object.
- **target**: Target object.
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
  object Obj : SomeInterface {}
  list<SomeInterface> ObjList;
  list<reference<SomeInterface>> RefList;
}

// CAPL
on key 'a' {
  // append default object or reference to list
  ObjList.PushBack();
  RefList.PushBack();

  // append reference with a specific target
  RefList.PushBack(Obj);
  RefList.PushBack("SomeNamespace::Obj");
}
```
