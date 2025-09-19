# distObjInterface::CreateObject

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

[distObjRef](../Objects/CAPLfunctiondistObjRef.md) <Interface> [distObjInterface](../Objects/CAPLfunctiondistObjInterface.md) <Interface>::CreateObject(distObjBlueprint <Interface> blueprint, char path[]);

[distObjRef](../Objects/CAPLfunctiondistObjRef.md) reverse<<Interface>> [distObjInterface](../Objects/CAPLfunctiondistObjInterface.md) <Interface>::CreateObject(distObjBlueprint reverse<<Interface>> blueprint, char path[]);

## Description

Creates a dynamic object from the blueprint.

**Note**  
If an error occurs in a test module, the error message will be reported as an error in test system. Otherwise a message will be written to the CANoe DE Family Write Window.

## Parameters

- **blueprint**: Blueprint which sets the attributes and virtual networks of the dynamic object.
- **path**: Fully qualified name of the dynamic object.

## Return Values

- New dynamic object.
- Invalid object if an error occurred.

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
  distObjBlueprint reverse<SomeInterface> rev_bp;

  bp = SomeInterface.CreateObjectBlueprint();
  rev_bp = SomeInterface.CreateReverseBlueprint();

  SomeInteface.CreateObject(bp, "SomeNamespace::Obj");
  SomeInteface.CreateObject(rev_bp, "SomeNamespace::RevObj");
}
```
