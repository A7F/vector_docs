[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjMemberBlueprintGetAttribute.md)

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjMemberBlueprint::GetAttribute

# distObjMemberBlueprint::GetAttribute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

- `long distObjMemberBlueprint::GetAttribute(char name[], char value[]);`
- `long distObjMemberBlueprint::GetAttribute(char name[], long& value);`
- `long distObjMemberBlueprint::GetAttribute(char name[], dword& value);`
- `long distObjMemberBlueprint::GetAttribute(char name[], int64& value);`
- `long distObjMemberBlueprint::GetAttribute(char name[], qword& value);`
- `long distObjMemberBlueprint::GetAttribute(char name[], double& value);`

## Description

Gets the value of an attribute that is set at the member blueprint. The attribute type must correspond to the overload that is called, otherwise an error code will be returned.

## Parameters

- **name**: Fully qualified name of the attribute.
- **value**: Value of the attribute.

## Return Values

- **0**: OK
- **1**: Invalid blueprint
- **2**: Attribute does not exist
- **3**: Attribute not found at blueprint
- **4**: Attribute has wrong type

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
  {
    long x;
    char str[42];

    bp.SomeEvent.GetAttribute("SomeNamespace::IntegerAttribute", x);
    bp.SomeEvent.GetAttribute("SomeNamespace::StringAttribute", str);

    write("%d", x);   // output: 42
    write("%s", str); // output: test
  }
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)