# SecurityLocalTransmitApplicationProtocol

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalTransmitApplicationProtocol(char applicationProtocolUserDefinedId[], byte payload[], dword payloadLength)
```

## Description

Transmits a special message of sequence of message specifically to the active Security Profile on the network.

The application protocol is specific to the active Security Profile on the network. Refer to the specific Security Source manual for more information about whether application protocols are available and what their functionality and purposes are.

## Parameters

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
