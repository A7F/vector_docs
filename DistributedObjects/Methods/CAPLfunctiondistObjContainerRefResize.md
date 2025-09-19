[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjContainerRefResize.md)

## CAPL Functions » Distributed Objects » distObjContainerRef::Resize

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Method Syntax
- `long distObjContainerRef <Typedef name>::Resize(dword size);`
- `long distObjContainerRef <Typedef name>::Resize(dword size, distObjBlueprint <Interface> blueprint);`

### Description
This method resizes the container. If the new size is greater than the old size, new elements will be added at the end. If the new size is less than the old size, elements will be removed at the end.

It requires that **`<Typedef name>`** refers to a list type.

The first overload is available for lists of objects and references. It appends default objects or empty references.

The second Overload is only available when **`<Typedef name>`** refers to a (nested) list of objects. Here the objects are created according to the blueprint argument.

### Parameters
- **size**: The new size of the container.
- **blueprint**: The blueprint according to which objects are created.

### Return Values
- **0**: OK
- **1**: An error occurred

### Example

```cpp
// vCDL
version 1.3;
namespace SomeNamespace {
  virtualnetwork SomeNetwork;
  interface SomeInterface {
    internal data int32 d;
  }
  list<SomeInterface> ObjList;
  list<reference<SomeInterface>> RefList;
}

// CAPL
on key 'a' {
  stack distObjBlueprint SomeInterface bp = SomeInterface.CreateObjectBlueprint();
  bp.d.SetVirtualNetwork(SomeNetwork);

  // resize with default objects or emtpy references
  ObjList.Resize(42);
  RefList.Resize(42);

  // resize with object blueprint
  ObjList.Resize(100, bp);
}
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
