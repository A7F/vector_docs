[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaSetPropertyRatio.md)

**CAPL Functions** » **Media API** » **MediaSetPropertyRatio**

# MediaSetPropertyRatio

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaSetPropertyRatio(dword objHandle, char propertyName[], dword numerator, dword denominator);
```

## Description

Sets a ratio as a 64-bit property value. Properties can be set on an object specific basis for a media type object (e.g. returned by [MediaGetMediaType](CAPLfunctionMediaGetMediaType.md)).

## Parameters

- **propertyName**: Name of the property to be set. For a list of properties that can be set by this function see [Media Properties](../CAPLfunctionsMediaProperties.md) and [Major Media Types / Subtypes](../CAPLfunctionsMediaMajorMediaTypesSubtypes.md).
- **objHandle**: Media type handle.
- **numerator**: Receives the numerator of the ratio.
- **denominator**: Receives the denominator of the ratio.

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
