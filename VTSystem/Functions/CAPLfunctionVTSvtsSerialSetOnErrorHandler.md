[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSerialSetOnErrorHandler.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSerialSetOnErrorHandler

# vtsSerialSetOnErrorHandler

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long vtsSerialSetOnErrorHandler (char Target[], char onErrorCallback[]);
```

## Description

Sets the callback that notifies when an error occurred during a send or receive operation.

The set callback has to have following signature: `void <[OnSerialError](CAPLfunctionVTSOnSerialError.md)>( dword errorFlags)`

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **onErrorCallback**: CAPL callback function name.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The passed callback does not have the required signature.

## Example

See example [vtsSerialConfigure](CAPLfunctionVTSvtsSerialConfigure.md)

[SerialSetOnErrorHandler](CAPLfunctionVTSSerialSetOnErrorHandler.md)
