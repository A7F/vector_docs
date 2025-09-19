[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalSetOperationParameter.md)

## SecurityLocalSetOperationParameter

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalSetOperationParameter

### Function Syntax

`long SecurityLocalSetOperationParameter(long key, qword value)`

### Description

Sets the operation parameter value of the specified key.

Which and how many operation parameters exist, which values are valid for an operation parameter differs from Security Source to Security Source.

Please refer to the Security Source specific manual to get more information about operation parameters. The manual can be opened from the Vector Security Manager on the OEM specific ribbon page.

### Parameters

- **long key**: the numeric identifier of the operation parameter.
- **qword value**: the new value of the operation parameter.

### Return Values

A value of 1 means that the action was successful. A value less than or equal to 0 means error.

- **1**: Success
- **0**: Error, no details
- **-1**: Invalid handle
- **-2**: Data incomplete
- **-4**: Security source error, no details
- **-6**: Not Implemented
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.
- **-11**: Operation Parameters are not supported by Vector Security Manager or used Security Source, you have to update to V2.5.7 or newer.

### Example

—
