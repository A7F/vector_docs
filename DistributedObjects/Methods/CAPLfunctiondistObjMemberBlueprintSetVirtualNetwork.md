# distObjMemberBlueprint::SetVirtualNetwork

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
void distObjMemberBlueprint::SetVirtualNetwork(char networkPath[]);
void distObjMemberBlueprint::SetVirtualNetwork(virtNet network);
```

## Description

Sets the virtual network of the member blueprint.

**Note**: An object member can only be part of a single virtual network. The previous virtual network will be replaced.

## Parameters

- **networkPath**: Fully qualified name of the virtual network.
- **network**: Virtual network.

## Return Values

—

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {
    consumed event int32 SomeEvent;
  }
  virtualNetwork SomeNetwork;
}

// CAPL
on key 'a' {
  distObjBlueprint SomeInterface bp;
  bp = SomeInterface.CreateObjectBlueprint();

  bp.SomeEvent.SetVirtualNetwork("SomeNamespace::SomeNetwork");
  bp.SomeEvent.SetVirtualNetwork(SomeNetwork);
}
```
