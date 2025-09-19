# setAttribute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `setAttribute(attributable object, attribute int32 attribute, long value); // form 1`
- `setAttribute(attributable object, attribute uint32 attribute, dword value); // form 2`
- `setAttribute(attributable object, attribute int64 attribute, int64 value); // form 3`
- `setAttribute(attributable object, attribute uint64 attribute, qword value); // form 4`
- `setAttribute(attributable object, attribute double attribute, double value); // form 5`
- `setAttribute(attributable object, attribute string attribute, char value[]); // form 6`
- `setAttribute(attributable object, char attribute[], long value); // form 7`
- `setAttribute(attributable object, char attribute[], dword value); // form 8`
- `setAttribute(attributable object, char attribute[], int64 value); // form 9`
- `setAttribute(attributable object, char attribute[], qword value); // form 10`
- `setAttribute(attributable object, char attribute[], double value); // form 11`
- `setAttribute(attributable object, char attribute[], char value[]); // form 12`

## Description

Writes an attribute value at an attributable object.

## Parameters

- **object**: Attributable object at which the attribute value is written.
- **attribute**: Attribute or attribute name for which the value is written.
- **value**: Attribute value.

## Return Values

- **0**: OK
- **1**: Attribute not allowed for object
- **2**: Value has wrong data type
- **6**: Attribute not runtime changeable
- **8**: Attribute changes in offline mode disallowed
- **-1**: Invalid object
- **-2**: Invalid attribute

## Example

```plaintext
// vCDL
version 1.4;
namespace SomeNamespace
{
  [Binding="Abstract"]
  object SomeObject {}
  attribute int32 MyAttribute { mutable; }
}

// CAPL
on start
{
  setAttribute(SomeObject, SomeNamespace::MyAttribute, 42);
}
```
