[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityOfNodeTransmitApplicationProtocol.md)

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityOfNodeTransmitApplicationProtocol

# SecurityOfNodeTransmitApplicationProtocol

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityOfNodeTransmitApplicationProtocol(char nodeName[], char networkName[], char applicationProtocolUserDefinedId[], byte payload[], dword payloadLength)
```

## Description

Transmits a special message of sequence of message protocol from the specified node on the specified network, specifically to the active Security Profile on the network.

The application protocol is specific to the active Security Profile on the network. Please refer to the Security Source specific manual to get more information about if there are application protocols available and their functionality and purpose.

You have to call [SecurityLocalStartControlSimulationNode](CAPLfunctionSecurityLocalStartControlSimulationNode.md) before this callback is called.

## Parameters

- **char nodeName[]**: The name of the node.
- **char networkName[]**: The name of the network the node is on.
- **char applicationProtocolUserDefinedId[]**: The Id of the application protocol, which can be specified in the Security Manager GUI.
- **byte payload[]**: The payload of the application protocol.
- **dword payloadLength**: The length of the payload in bytes.

## Return Values

A Value of 1 means that the action was successful. A value less than or equal to 0 means error.

- **1**: Success.
- **0**: Error, no details.
- **-1**: Invalid handle.
- **-2**: Data incomplete.
- **-3**: Signal length does not fit.
- **-4**: Security source error, no details.
- **-6**: Not supported.
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
