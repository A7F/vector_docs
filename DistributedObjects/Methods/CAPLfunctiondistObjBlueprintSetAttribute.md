# distObjBlueprint::SetAttribute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

- `long distObjBlueprint *::SetAttribute(char name[], char value[]);`
- `long distObjBlueprint *::SetAttribute(char name[], long value);`
- `long distObjBlueprint *::SetAttribute(char name[], dword value);`
- `long distObjBlueprint *::SetAttribute(char name[], int64 value);`
- `long distObjBlueprint *::SetAttribute(char name[], qword value);`
- `long distObjBlueprint *::SetAttribute(char name[], double value);`

### Description

Sets an attribute at the blueprint. The attribute type must correspond to the overload that is called. Otherwise, an error code will be returned. Integer types will be converted if they fall in the range of the attribute type.

### Parameters

- **name**: Fully qualified name of the attribute.
- **value**: Value of the attribute.

### Return Values

- **0**: OK
- **1**: Invalid blueprint
- **2**: Attribute does not exist
- **4**: Attribute has wrong type

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
}
```
