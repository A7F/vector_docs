[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSerialReceive.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSerialReceive

# vtsSerialReceive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long vtsSerialReceive (char Target[], byte buffer[], dword size);
```

## Description

Starts receiving blocks of bytes from the serial port of the specified VT7001 channel. Received data is copied to the specified buffer. The data can only be accessed in the [OnSerialReceive](CAPLfunctionVTSOnSerialReceive.md) callback.

- The operation works continuously if issued once.
- If another receive operation is given, the result buffer will change to that one given by the last receive operation.
- A callback handler has to be set for notification when data has been received. See [SerialSetOnReceiveHandler](CAPLfunctionVTSSerialSetOnReceiveHandler.md).
- Another callback handler can be set to notify of errors in later stages of the send operation. See [SerialSetOnErrorHandler](CAPLfunctionVTSSerialSetOnErrorHandler.md).

The used serial port has to be opened first.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **buffer**: An array of bytes where received data is copied to. The buffer is only valid within the [OnSerialReceive](CAPLfunctionVTSOnSerialReceive.md) callback.
- **size**: Maximum number of Bytes which can be received at a time. Must have a value > 0 and < 65.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: One of the parameters has an invalid value.
- **-5**: Serial port is not open.

## Example

See example [vtsSerialConfigure](CAPLfunctionVTSvtsSerialConfigure.md)

[SerialReceive](CAPLfunctionVTSSerialReceive.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
