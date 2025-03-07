[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjContainerRefErase.md)

# distObjContainerRef::Erase

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjContainerRef::Erase

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
long distObjContainerRef <Typedef name>::Erase(dword index);
```

## Description

Replaces an object at the given index with an invalid object. It requires that **<Typedef name>** refers to an object array type. The length of the container is not changed.

## Parameters

- **index**: Index at which to remove the object.

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
  // remove an object
  ObjList.Erase(2);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)