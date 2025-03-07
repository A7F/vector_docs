[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjBlueprintCopyFromObject.md)

**CAPL Functions** » **Distributed Objects** » **distObjBlueprint::CopyFromObject**

# distObjBlueprint::CopyFromObject

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
void distObjBlueprint<Interface>::CopyFromObject(distObjRef<Interface> object);
```

## Description

Recursively copies all attributes and virtual network from the given object and its members to the blueprint.

## Parameters

- **object**: Object from which to copy.

## Return Values

—

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {}

  [IntegerAttribute=42, StringAttribute="test"]
  object Obj : SomeInterface {}

  attribute int32 IntegerAttribute;
  attribute string StringAttribute;
}

// CAPL
on key 'a' {
  distObjBlueprint SomeInterface bp;
  bp = SomeInterface.CreateObjectBlueprint();
  bp.CopyFromObject(Obj);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)