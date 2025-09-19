# distObjMemberBlueprint

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`distObjMemberBlueprint`

## Method Syntax

- [distObjMemberBlueprint::GetAttribute](../Methods/CAPLfunctiondistObjMemberBlueprintGetAttribute.md)
- [distObjMemberBlueprint::RemoveAttribute](../Methods/CAPLfunctiondistObjMemberBlueprintRemoveAttribute.md)
- [distObjMemberBlueprint::RemoveVirtualNetwork](../Methods/CAPLfunctiondistObjMemberBlueprintRemoveVirtualNetwork.md)
- [distObjMemberBlueprint::SetAttribute](../Methods/CAPLfunctiondistObjMemberBlueprintSetAttribute.md)
- [distObjMemberBlueprint::SetVirtualNetwork](../Methods/CAPLfunctiondistObjMemberBlueprintSetVirtualNetwork.md)
- [distObjMemberBlueprint::SetInitialValue](../Methods/CAPLfunctiondistObjMemberBlueprintSetInitialValue.md)

## Description

A type for configuring the attributes and virtual network of an object blueprint member. This type cannot be used in declarations.

## Parameters

—

## Selectors

—

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
