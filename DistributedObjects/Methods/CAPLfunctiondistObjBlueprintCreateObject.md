# distObjBlueprint::CreateObject

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjBlueprint::CreateObject

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

`distObjRef <Interface> distObjBlueprint <Interface>::CreateObject(char path[]);`

## Description

Creates a dynamic object from the blueprint.

## Parameters

- **path**: Fully qualified name of the dynamic object.

## Return Values

New dynamic object with the given path.

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {}
}

// CAPL
on key 'a' {
  distObjBlueprint SomeInterface bp;
  bp = SomeInterface.CreateObjectBlueprint();
  bp.CreateObject("SomeNamespace::Obj");
}
```
