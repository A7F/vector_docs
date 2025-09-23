# SecurityOfNodeGetOperationParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SecurityOfNodeGetOperationParameter(char nodeName[], char networkName[], long key, qword value, char description[], dword descriptionLength)
```

## Description

Gets the value and description of the operation parameter of the specified key at the specified node and network.

You have to call [SecurityLocalStartControlSimulationNode](CAPLfunctionSecurityLocalStartControlSimulationNode.md) before this callback is called.

Which and how many operation parameters exist, which values are valid for an operation parameter differs from Security Source to Security Source.

Please refer to the Security Source specific manual to get more information about operation parameters. The manual can be opened from the Vector Security Manager on the OEM specific ribbon page.

## Parameters

- **char nodeName[]**: Name of the node.
- **char networkName[]**: Name of the network in which the node is located.
- **long key**: The numeric identifier of the operation parameter.
- **qword value**: The current value of the operation parameter. [out]
- **char description[]**: The buffer for the description of the parameter. Usable for output and documentation of the parameter i.e. Test Units if the buffer is too small the description is truncated. [in/out]
- **dword descriptionLength**: The length of the description buffer [in]. If the specified length is zero, no description is returned (faster). The value of descriptionLength is changed to the length of the description if the specified buffer is not completely used. [out]

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
