[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSerialSetOnSendHandler.md)

**CAPL Functions** » **VT System** » **vtsSerialSetOnSendHandler**

# vtsSerialSetOnSendHandler

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long vtsSerialSetOnSendHandler (char Target[], char onSendCallback []);
```

## Description

Sets the callback that notifies when a send operation on the serial port of the specified channel is completed successfully.

The set callback must have the following signature: `void <OnSerialSend>( byte sendBuffer[], dword number)`

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **onSendCallback**: CAPL callback function name.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The passed callback does not have the required signature, i.e., number or type of the parameters are different than expected.

## Example

See example [vtsSerialConfigure](CAPLfunctionVTSvtsSerialConfigure.md)

[SerialSetOnSendHandler](CAPLfunctionVTSSerialSetOnSendHandler.md)
