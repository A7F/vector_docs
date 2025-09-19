[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaGetPropertySize.md)

**CAPL Functions** » **Media API** » **MediaGetPropertySize**

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

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
