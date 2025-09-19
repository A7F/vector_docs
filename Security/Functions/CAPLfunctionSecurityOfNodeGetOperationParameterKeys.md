[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityOfNodeGetOperationParameterKeys.md)

**CAPL Functions** » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityOfNodeGetOperationParameterKeys

# SecurityOfNodeGetOperationParameterKeys

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SecurityOfNodeGetOperationParameterKeys(char nodeName[], char networkName[], long category, dword keyBuffer[], dword keyBufferLength)
```

## Description

Gets the list of operation parameter keys, supported by the currently loaded Security Source.

Which and how many operation parameters exist, which values are valid for an operation parameter differs from Security Source to Security Source.

Please refer to the Security Source specific manual to get more information about operation parameters. The manual can be opened from the Vector Security Manager on the OEM specific ribbon page.

## Parameters

- **char nodeName[]**: Name of the node.
- **char networkName[]**: Name of the network in which the node is located.
- **long category**: The category of the operation parameters, 0 = all operation parameters.
- **dword keyBuffer[]**: The allocated buffer in which the operation parameter keys are written by the Security Source. [out]
- **dword keyBufferLength**: The capacity of the keyBuffer [in], the number of operation parameter keys in the keyBuffer. [out]

## Return Values

A value of 1 means that the action was successful. A value less than or equal to 0 means error.

- **1**: Success.
- **0**: Error, no details.
- **-1**: Invalid handle.
- **-2**: Data incomplete.
- **-4**: Security source error, no details.
- **-6**: Not Implemented.
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.
- **-11**: Operation Parameters are not supported by Vector Security Manager or used Security Source, you have to update to V2.5.7 or newer.

## Example

—

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
