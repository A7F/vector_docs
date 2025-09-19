# distObjInterface

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `distObjInterface *`
- `distObjInterface <Interface>`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [distObjInterface <Interface>::CreateObject](../Methods/CAPLfunctiondistObjInterfaceCreateObject.md)
- [distObjInterface <Interface>::CreateObjectBlueprint](../Methods/CAPLfunctiondistObjInterfaceCreateObjectBlueprint.md)
- [distObjInterface <Interface>::CreateReverseObjectBlueprint](../Methods/CAPLfunctiondistObjInterfaceCreateReverseObjectBlueprint.md)
- [distObjInterface <Interface>::DestroyObject](../Methods/CAPLfunctiondistObjInterfaceDestroyObject.md)

## Description

A type for creating blueprints and dynamic distributed objects.

All `distObjInterface` types are singleton types. The value of each type is bound to the name of the corresponding interface.

The types are not available for user declarations.

## Parameters

- **Interface**: The optionally qualified name of a distributed object interface. It is also possible to take the reverse of an interface by using the `reverse<…>` operator.

## Selectors

- **Selector**: `<Member Name>`
- **Type**: `distObjInterfaceMember <Member Path>`
- **Access Limitation**: Read only

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

  bp = SomeInterface.CreateObjectBlueprint();
  obj = SomeInterface.CreateObject(bp, "SomeNamespace::Obj");

  SomeInterface.DestroyObject("SomeNamespace::Obj");
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
