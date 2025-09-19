[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalGetOperationParameter.md)

**CAPL Functions** » **Security** » **SecurityLocalGetOperationParameter**

# SecurityLocalGetOperationParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalGetOperationParameter(long key, qword value, char description[], dword descriptionLength)
```

## Description

Gets the value and description of the operation parameter of the specified key.

Which and how many operation parameters exist, which values are valid for an operation parameter differs from Security Source to Security Source.

Please refer to the Security Source specific manual to get more information about operation parameters. The manual can be opened from the Vector Security Manager on the OEM specific ribbon page.

## Parameters

- **long key**: the numeric identifier of the operation parameter.
- **qword value**: the current value of the operation parameter. [out]
- **char description[]**: the buffer for the description of the parameter. Usable for output and documentation of the parameter i.e. Test Units if the buffer is too small the description is truncated. [in/out]
- **dword descriptionLength**: the length of the description buffer [in]. If the specified length is zero, no description is returned (faster). The value of descriptionLength is changed to the length of the description if the specified buffer is not completely used. [out]

## Return Values

- **-11**: Operation Parameters are not supported by Vector Security Manager or used Security Source, you have to update to V2.5.7 or newer.

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
