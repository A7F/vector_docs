# distObjBlueprint::Clear

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjBlueprint::Clear

**Valid for:** CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

void [distObjBlueprint](../Objects/CAPLfunctiondistObjBlueprint.md) *::Clear();

## Description

Removes all attributes and virtual networks from the blueprint.

## Parameters

—

## Return Values

—

## Example

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

  bp.Clear();
}
```
