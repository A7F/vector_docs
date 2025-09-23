[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSerialSetOnReceiveHandler.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSerialSetOnReceiveHandler

# vtsSerialSetOnReceiveHandler

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long vtsSerialSetOnReceiveHandler (char Target[], char onReceiveCallback []);
```

## Description

Sets the callback that notifies when data has been received on the serial port of the specified channel.

The set callback has to have following signature: `void <OnSerialReceive>( byte bffer[], dword number)`

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **onReceiveCallback**: CAPL callback function name.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The passed callback does not have the required signature.

## Example

See example [vtsSerialConfigure](CAPLfunctionVTSvtsSerialConfigure.md)

[SerialSetOnReceiveHandler](CAPLfunctionVTSSerialSetOnReceiveHandler.md)
