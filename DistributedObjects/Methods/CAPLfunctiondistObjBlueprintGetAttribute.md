[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjBlueprintGetAttribute.md)

**CAPL Functions** » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjBlueprint::GetAttribute

# distObjBlueprint::GetAttribute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

- `long distObjBlueprint *::GetAttribute(char name[], char value[]);`
- `long distObjBlueprint *::GetAttribute(char name[], long& value);`
- `long distObjBlueprint *::GetAttribute(char name[], dword& value);`
- `long distObjBlueprint *::GetAttribute(char name[], int64& value);`
- `long distObjBlueprint *::GetAttribute(char name[], qword& value);`
- `long distObjBlueprint *::GetAttribute(char name[], double& value);`

## Description

Gets the value of an attribute that is set at the blueprint. The attribute type must correspond to the overload that is called, otherwise an error code will be returned.

## Parameters

- **namespace**: Fully qualified name of the attribute.
- **value**: Value of the attribute.

## Return Values

- **0**: OK
- **1**: Invalid blueprint
- **2**: Attribute does not exist
- **3**: Attribute not found at blueprint
- **4**: Attribute has wrong type

## Example

```c
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
  {
    long x;
    char str[42];

    bp.GetAttribute("SomeNamespace::IntegerAttribute", x);
    bp.GetAttribute("SomeNamespace::StringAttribute", str);

    write("%d", x);   // output: 42
    write("%s", str); // output: test
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)