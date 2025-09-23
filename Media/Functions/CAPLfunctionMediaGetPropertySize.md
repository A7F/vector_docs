# MediaGetPropertySize

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaGetPropertySize(dword objHandle, char propertyName[], dword& width, dword& height);
```

## Description

Retrieves a property whose value is a size, expressed as a width and height. Properties can be retrieved on an object specific basis for a media type object (e.g. returned by [MediaGetMediaType](CAPLfunctionMediaGetMediaType.md)).

## Parameters

- **propertyName**: Name of the property to be retrieved. For a list of properties that can be retrieved by this function see [Media Properties](../CAPLfunctionsMediaProperties.md) and [Major Media Types / Subtypes](../CAPLfunctionsMediaMajorMediaTypesSubtypes.md).
- **objHandle**: Media type handle.
- **width**: Receives the width.
- **height**: Receives the height.

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—
