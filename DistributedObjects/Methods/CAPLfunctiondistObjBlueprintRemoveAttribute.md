[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjBlueprintRemoveAttribute.md)

## CAPL Functions » Distributed Objects » distObjBlueprint::RemoveAttribute

### distObjBlueprint::RemoveAttribute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Method Syntax

```plaintext
long distObjBlueprint *::RemoveAttribute(char name);
```

### Description

Removes an attribute from the blueprint.

### Parameters

- **name**: Fully qualified name of the attribute.

### Return Values

- **0**: OK
- **1**: Invalid blueprint
- **2**: Attribute does not exist
- **3**: Attribute not found at blueprint

### Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {}
  attribute int32 IntegerAttribute;
  attribute string StringAttribute;
}

// CAPL
on key 'a' {
  distObjBlueprint SomeInterface bp;
  bp = SomeInterface.CreateObjectBlueprint();

  bp.SetAttribute("SomeNamespace::IntegerAttribute", 42);
  bp.SetAttribute("SomeNamespace::StringAttribute", "test");

  bp.RemoveAttribute("SomeNamespace::IntegerAttribute");
  bp.RemoveAttribute("SomeNamespace::StringAttribute");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)