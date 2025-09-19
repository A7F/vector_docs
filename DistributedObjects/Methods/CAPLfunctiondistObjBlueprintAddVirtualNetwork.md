# distObjBlueprint::AddVirtualNetwork

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
void distObjBlueprint *::AddVirtualNetwork(char networkPath[]);
void distObjBlueprint *::AddVirtualNetwork(virtNet network);
```

## Description

Adds a virtual network to the blueprint.

## Parameters

- **networkPath**: Fully qualified name of the virtual network to add.
- **network**: Virtual network to add.

## Return Values

—

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {}
  virtualNetwork SomeNetwork;
}

// CAPL
on key 'a' {
  distObjBlueprint SomeInterface bp;
  bp = SomeInterface.CreateObjectBlueprint();
  bp.AddVirtualNetwork("SomeNamespace::SomeNetwork");
  bp.AddVirtualNetwork(SomeNetwork);
}
```
