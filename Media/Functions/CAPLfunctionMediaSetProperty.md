[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaSetProperty.md)

**CAPL Functions** » [Media API](../CAPLfunctionsMediaOverview.md) » MediaSetProperty

# MediaSetProperty

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long MediaSetProperty(dword objHandle, char propertyName[], int64 value); // form 1`
- `long MediaSetProperty(dword objHandle, char propertyName[], dword length, char value[]); // form 2`
- `long MediaSetProperty(dword objHandle, char propertyName[], dword length, byte value[]); // form 3`

## Description

The behavior of an object can be configured using properties. Properties can be set on an object specific basis for a media type object (e.g. returned by [MediaGetMediaType](CAPLfunctionMediaGetMediaType.md)).

## Parameters

- **propertyName**: Name of the property to be set. For a list of properties that can be set by this function see [Media Properties](../CAPLfunctionsMediaProperties.md) and [Major Media Types / Subtypes](../CAPLfunctionsMediaMajorMediaTypesSubtypes.md).
- **objHandle**: Media type handle.
- **length (string overload only)**: Length of the value buffer passed.
- **value**: New value of the property.

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
