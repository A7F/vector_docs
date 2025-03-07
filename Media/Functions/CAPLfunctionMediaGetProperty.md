[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaGetProperty.md)

**CAPL Functions** » [Media API](../CAPLfunctionsMediaOverview.md) » MediaGetProperty

# MediaGetProperty

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long MediaGetProperty(dword objHandle, char propertyName[], dword& value); // form 1`
- `long MediaGetProperty(dword objHandle, char propertyName[], dword length, char value[]); // form 2`
- `long MediaGetProperty(dword objHandle, char propertyName[], qword& value); // form 3`
- `long MediaGetProperty(dword objHandle, char propertyName[], dword length, byte value[]); // form 4`

## Description

The behavior of an object can be configured using properties. Properties can be retrieved on an object-specific basis for a media type object (e.g., returned by [MediaGetMediaType](CAPLfunctionMediaGetMediaType.md)).

## Parameters

- **propertyName**: Name of the property to be retrieved. For a list of properties that can be retrieved by this function see [Media Properties](../CAPLfunctionsMediaProperties.md) and [Major Media Types / Subtypes](../CAPLfunctionsMediaMajorMediaTypesSubtypes.md).
- **objHandle**: Media type handle.
- **length**: Number of characters in **value**. Set to [elCount](../../Other/Functions/CAPLfunctionElCount.md)(value).
- **value**: Returned value of the property.

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)