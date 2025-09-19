# distObjInterface::DestroyObject

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjInterface::DestroyObject

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
long distObjInterface <Interface>::DestroyObject(distObjRef <Interface> object);
long distObjInterface <Interface>::DestroyObject(distObjRef reverse<<Interface>> object);
```

## Description

Destroys a dynamic object.

**Note**: If an error occurs in a test module, the error message will be reported as an error in the test system. Otherwise, a message will be written to the CANoe DE Family Write Window.

## Parameters

- **object**: Dynamic object to be destroyed.

## Return Values

- **0**: OK
- **1**: An error occurred

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {}
}

// CAPL
on key 'a' {
  distObjRef SomeInterface obj;
  distObjRef reverse<SomeInterface> rev_obj;

  distObjBlueprint SomeInterface bp;
  distObjBlueprint reverse<SomeInterface> rev_bp;

  bp = SomeInterface.CreateObjectBlueprint();
  rev_bp = SomeInterface.CreateReverseBlueprint();

  obj = SomeInteface.CreateObject(bp, "SomeNamespace::Obj");
  rev_obj = SomeInteface.CreateObject(rev_bp, "SomeNamespace::RevObj");

  SomeInterface.DestroyObject(obj);
  SomeInterface.DestroyObject(rev_obj);
}
```
