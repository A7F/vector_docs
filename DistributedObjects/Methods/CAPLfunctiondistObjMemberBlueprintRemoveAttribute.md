# distObjMemberBlueprint::RemoveAttribute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
long distObjMemberBlueprint::RemoveAttribute(char name[]);
```

## Description

Removes an attribute from the member blueprint.

## Parameters

- **name**: Fully qualified name of the attribute.

## Return Values

- **0**: OK
- **1**: Invalid blueprint
- **2**: Attribute does not exist
- **3**: Attribute not found at blueprint

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {
    consumed event int32 SomeEvent;
  }
  attribute int32 IntegerAttribute;
  attribute string StringAttribute;
}

// CAPL
on key 'a' {
  distObjBlueprint SomeInterface bp;
  bp = SomeInterface.CreateObjectBlueprint();

  bp.SomeEvent.SetAttribute("SomeNamespace::IntegerAttribute", 42);
  bp.SomeEvent.SetAttribute("SomeNamespace::StringAttribute", "test");

  bp.SomeEvent.RemoveAttribute("SomeNamespace::IntegerAttribute");
  bp.SomeEvent.RemoveAttribute("SomeNamespace::StringAttribute");
}
```
