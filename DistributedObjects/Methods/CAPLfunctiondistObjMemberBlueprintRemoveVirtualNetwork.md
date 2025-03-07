[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjMemberBlueprintRemoveVirtualNetwork.md)

**CAPL Functions** » **Distributed Objects** » **distObjMemberBlueprint::RemoveVirtualNetwork**

# distObjMemberBlueprint::RemoveVirtualNetwork

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
void distObjMemberBlueprint::RemoveVirtualNetwork();
```

## Description

Removes the virtual network from the member blueprint.

## Parameters

—

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
  bp.SomeEvent.RemoveVirtualNetwork("SomeNamespace::SomeNetwork");

  bp.SomeEvent.SetVirtualNetwork(SomeNetwork);
  bp.SomeEvent.RemoveVirtualNetwork(SomeNetwork);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)