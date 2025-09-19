# distObjBlueprint

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `distObjBlueprint *`
- `distObjBlueprint <Interface>`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [distObjBlueprint *::AddVirtualNetwork](../Methods/CAPLfunctiondistObjBlueprintAddVirtualNetwork.md)
- [distObjBlueprint *::Clear](../Methods/CAPLfunctiondistObjBlueprintClear.md)
- [distObjBlueprint *::GetAttribute](../Methods/CAPLfunctiondistObjBlueprintGetAttribute.md)
- [distObjBlueprint *::RemoveAttribute](../Methods/CAPLfunctiondistObjBlueprintRemoveAttribute.md)
- [distObjBlueprint *::RemoveVirtualNetwork](../Methods/CAPLfunctiondistObjBlueprintRemoveVirtualNetwork.md)
- [distObjBlueprint *::SetAttribute](../Methods/CAPLfunctiondistObjBlueprintSetAttribute.md)
- [distObjBlueprint <Interface>::CopyFromObject](../Methods/CAPLfunctiondistObjBlueprintCopyFromObject.md)
- [distObjBlueprint <Interface>::CreateObject](../Methods/CAPLfunctiondistObjBlueprintCreateObject.md)

## Description

A blueprint type for dynamically creating distributed objects.

Variables are initialized with an invalid blueprint. The blueprints have a copy semantic when they are assigned (assignment operator, call-by-value parameter, function return value). Stack allocated variables and temporary values are automatically destroyed when they go out of scope. Blueprint types cannot be used for copy-restore parameters.

## Parameters

- **Interface**: The optionally qualified name of a distributed object interface. It is also possible to take the reverse of an interface by using the `reverse<…>` operator.

## Selectors

- **IsValid**: 1 if blueprint is valid, 0 otherwise. Type: `dword`, Access: Read only
- **<Member Name>**: Access the member blueprint. Type: `distObjMemberBlueprint`, Access: Read only
- **<Embedded Member Name>**: Access the embedded member blueprint. Type: `distObjBlueprint <Embedded Member Interface>`, Access: Read only

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {}
  attribute int32 SomeAttribute;
}

// CAPL
on start {
  distObjRef SomeInterface obj;

  distObjBlueprint SomeInterface bp;
  write("%d", bp.IsValid); // output: 0

  bp = SomeInterface.CreateObjectBlueprint();
  write("%d", bp.IsValid); // output: 1

  obj = bp.CreateObject("SomeNamespace::Obj");
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
