# getAttribute

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » getAttribute

**Valid for**: [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `getAttribute(attributable object, attribute int32 attribute, long& value); // form 1`
- `getAttribute(attributable object, attribute uint32 attribute, dword& value); // form 2`
- `getAttribute(attributable object, attribute int64 attribute, int64& value); // form 3`
- `getAttribute(attributable object, attribute uint64 attribute, qword& value); // form 4`
- `getAttribute(attributable object, attribute double attribute, double& value); // form 5`
- `getAttribute(attributable object, attribute string attribute, char value[]); // form 6`
- `getAttribute(attributable object, char attribute[], long& value); // form 7`
- `getAttribute(attributable object, char attribute[], dword& value); // form 8`
- `getAttribute(attributable object, char attribute[], int64& value); // form 9`
- `getAttribute(attributable object, char attribute[], qword& value); // form 10`
- `getAttribute(attributable object, char attribute[], double& value); // form 11`
- `getAttribute(attributable object, char attribute[], char value[]); // form 12`

## Description

Reads an attribute value from an attributable object.

## Parameters

- **object**: Attributable object at which the attribute value is read.
- **attribute**: Attribute or attribute name for which the value is read.
- **value**: Out-parameter for the attribute value.

## Return Values

- **0**: OK
- **1**: Attribute not allowed for object
- **-1**: Invalid object
- **-2**: Invalid attribute
- **-4**: Value has wrong data type
- **-5**: String buffer too small
- **-6**: String conversion error

## Example

```plaintext
// vCDL
version 1.4;
namespace SomeNamespace
{
  [Binding="Abstract"]
  object SomeObject {}
}

// CAPL
on start
{
  char str[100];
  getAttribute(SomeObject, _SystemAttributes::Binding, str);
  write("Binding: %s", str);
}
```
