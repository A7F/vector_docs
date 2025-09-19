[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaSetPropertySize.md)

**CAPL Functions** » **Media API** » **MediaSetPropertySize**

# MediaSetPropertySize

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaSetPropertySize(dword objHandle, char propertyName[], dword width, dword height);
```

## Description

Sets width and height as a single 64-bit property value. Properties can be set on an object specific basis for a media type object (e.g. returned by [MediaGetMediaType](CAPLfunctionMediaGetMediaType.md)).

## Parameters

- **propertyName**: Name of the property to be retrieved. For a list of properties that can be set by this function see [Media Properties](../CAPLfunctionsMediaProperties.md) and [Major Media Types / Subtypes](../CAPLfunctionsMediaMajorMediaTypesSubtypes.md).
- **objHandle**: Media type handle.
- **width**: Receives the width.
- **height**: Receives the height.

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)
