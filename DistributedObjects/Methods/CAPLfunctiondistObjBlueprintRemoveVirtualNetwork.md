[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjBlueprintRemoveVirtualNetwork.md)

**CAPL Functions** » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjBlueprint::RemoveVirtualNetwork

# distObjBlueprint::RemoveVirtualNetwork

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
void distObjBlueprint *::RemoveVirtualNetwork(char networkPath[]);
void distObjBlueprint *::RemoveVirtualNetwork(virtNet network);
```

## Description

This method removes a virtual network from the blueprint.

## Parameters

- **networkPath**: Fully qualified name of the virtual network to remove.
- **network**: Virtual network to remove.

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
  bp.RemoveVirtualNetwork("SomeNamespace::SomeNetwork");

  bp.AddVirtualNetwork(SomeNetwork);
  bp.RemoveVirtualNetwork(SomeNetwork);
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)