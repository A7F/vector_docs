[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjContainerRefPopBack.md)

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjContainerRef::PopBack

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)