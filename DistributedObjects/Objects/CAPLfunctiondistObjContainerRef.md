# distObjContainerRef

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `distObjContainerRef *`
- `distObjContainerRef <Typedef name>`

## Method Syntax

- [distObjContainerRef <Typedef name>::Create](../Methods/CAPLfunctiondistObjContainerRefCreate.md)
- [distObjContainerRef <Typedef name>::Erase](../Methods/CAPLfunctiondistObjContainerRefErase.md)
- [distObjContainerRef <Typedef name>::PopBack](../Methods/CAPLfunctiondistObjContainerRefPopBack.md)
- [distObjContainerRef <Typedef name>::PushBack](../Methods/CAPLfunctiondistObjContainerRefPushBack.md)
- [distObjContainerRef <Typedef name>::Resize](../Methods/CAPLfunctiondistObjContainerRefResize.md)

## Description

References a container of distributed objects or references.

The types provide an overload for the subscript operator to access the elements which have a [distObjRef](CAPLfunctiondistObjRef.md), [distObjReferenceRef](CAPLfunctiondistObjReferenceRef.md), or `distObjContainerRef` type. The wildcard container type (`distObjContainerRef *`) cannot be used with the subscript operator but it is possible to downcast it with a runtime check to a more specialized type.

The leaf elements of containers can be iterated over with a for loop (same syntax as C++ range-based for loop). The leaf elements are visited in the same order as in a depth-first search. Invalid elements (only possible in object containers) are skipped.

Containers are **not** covariant in their element type, as they are mutable.

## Parameters

- **Typedef name**: The fully qualified name of a distributed object or reference container.

## Selectors

- **Name**: Name of the reference.  
  **Type**: `char[]`  
  **Access Limitation**: Read only

- **Path**: Path of the reference.  
  **Type**: `char[]`  
  **Access Limitation**: Read only

- **IsValid**: 1 if a valid reference is referenced, 0 otherwise.  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **Length**: Number of elements.  
  **Type**: `dword`  
  **Access Limitation**: Read-write only for list, Read only for array

## Example

```cpp
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {
    internal data int32 d;
  }
  typedef ObjListType  = list<SomeInterface>;
  typedef ObjArrayType = array<SomeInterface, 42>;
  typedef RefListType  = list<reference<SomeInterface>>;
  typedef RefArrayType = array<reference<SomeInterface>, 42>;

  ObjListType  ObjList;
  ObjArrayType ObjArray;
  RefListType  RefList;
  RefArrayType RefArray;
  array<array<SomeInterface, 42>, 42> NestedArray;
}

// CAPL
on start {
  UseVariable();
  SubscriptOperator();
  Iterate();
}

void UseVariable() {
  // variable declarations
  distObjContainerRef * c1;
  distObjContainerRef SomeNamespace::ObjListType  c2 = ObjList;
  distObjContainerRef SomeNamespace::ObjArrayType c3 = ObjArray;
  distObjContainerRef SomeNamespace::RefListType  c4 = RefList;
  distObjContainerRef SomeNamespace::RefArrayType c5 = RefArray;

  // check if a valid container is referenced
  write("%d", c1.IsValid); // output: 0
  write("%d", c2.IsValid); // output: 1

  // type conversions (checked at runtime)
  c1 = c2;                                  // implicit upcast
  c2 = (distObjContainerRef ObjListType)c1; // explicit downcast

  // check the name and path of the container
  write("%s", c1.Name); // output: ObjList
  write("%s", c1.Path); // output: SomeNamespace::ObjList
}

void SubscriptOperator() {
  write("%s", ObjArray[2].Name);       // output: ObjArray[2]
  write("%s", RefArray[2].Name);       // output: RefArray[2]
  write("%s", NestedArray[2][3].Name); // output: NestedArray[2][3]
}

void Iterate() {
  for (distObjRef SomeInterface obj : ObjArray) {
    write("%s", obj.Path)
  }
  for (distObjReferenceRef SomeInterface ref : RefArray) {
    write("%s", ref.Path)
  }
  for (distObjRef SomeInterface obj : NestedArray) {
    write("%s", obj.Path)
  }
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
