[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjMemberBlueprintSetAttribute.md)

## distObjMemberBlueprint::SetAttribute

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjMemberBlueprint::SetAttribute

**Valid for**: [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Method Syntax

- `long distObjMemberBlueprint::SetAttribute(char name[], char value[]);`
- `long distObjMemberBlueprint::SetAttribute(char name[], long value);`
- `long distObjMemberBlueprint::SetAttribute(char name[], dword value);`
- `long distObjMemberBlueprint::SetAttribute(char name[], int64 value);`
- `long distObjMemberBlueprint::SetAttribute(char name[], qword value);`
- `long distObjMemberBlueprint::SetAttribute(char name[], double value);`

### Description

Sets an attribute at the member blueprint.

The attribute type must correspond to the overload that is called. Otherwise, an error code will be returned. Integer types will be converted if they fall in the range of the attribute type.

### Parameters

- **name**: Fully qualified name of the attribute.
- **value**: Value of the attribute.

### Return Values

- **0**: OK
- **1**: Invalid blueprint
- **2**: Attribute does not exist
- **4**: Attribute has wrong type

### Example

```cpp
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
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)