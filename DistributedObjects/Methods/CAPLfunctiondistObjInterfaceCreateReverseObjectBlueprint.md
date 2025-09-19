# distObjInterface::CreateReverseObjectBlueprint

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

[distObjBlueprint](../Objects/CAPLfunctiondistObjBlueprint.md) reverse<<Interface>> [distObjInterface](../Objects/CAPLfunctiondistObjInterface.md) <Interface>::CreateReverseObjectBlueprint();

[distObjBlueprint](../Objects/CAPLfunctiondistObjBlueprint.md) reverse<<Interface>> [distObjInterface](../Objects/CAPLfunctiondistObjInterface.md) <Interface>::CreateReverseObjectBlueprint(distObjRef reverse<<Interface>> object);

## Description

Creates a blueprint for the reverse of the given interface.

## Parameters

- **object**: Object from which to copy attributes and virtual networks.

## Return Values

- New object blueprint.
- Invalid object blueprint if an error occurred.

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {}
  object Obj : reverse<SomeInterface> {}
}

// CAPL
on key 'a' {
  distObjBlueprint reverse<SomeInterface> bp;

  bp = SomeInterface.CreateReverseObjectBlueprint();
  bp = SomeInterface.CreateReverseObjectBlueprint(Obj);
}
```
