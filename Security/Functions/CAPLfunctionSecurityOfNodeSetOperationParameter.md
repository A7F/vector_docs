[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityOfNodeSetOperationParameter.md)

## SecurityOfNodeSetOperationParameter

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityOfNodeSetOperationParameter

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```
long SecurityOfNodeSetOperationParameter(char nodeName[], char networkName[], long key, qword value)
```

### Description

Sets the operation parameter value of the specified key at the specified node and network. You have to call [SecurityLocalStartControlSimulationNode](CAPLfunctionSecurityLocalStartControlSimulationNode.md) before this callback is called. Which and how many operation parameters exist, which values are valid for an operation parameter differs from Security Source to Security Source.

Refer to the Security Source specific manual to get more information about operation parameters. The manual can be opened from the Vector Security Manager on the OEM specific ribbon page.

### Parameters

- **char nodeName[]**: Name of the node.
- **char networkName[]**: Name of the network in which the node is located.
- **long key**: Numeric identifier of the operation parameter.
- **qword value**: New value of the operation parameter.

### Return Values

- **1**: Success.
- **0**: Error, no details.
- **-1**: Invalid handle.
- **-2**: Data incomplete.
- **-4**: Security source error, no details.
- **-6**: Not implemented.
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.
- **-11**: Operation Parameters are not supported by Vector Security Manager or used Security Source, you have to update to V2.5.7 or newer.

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
