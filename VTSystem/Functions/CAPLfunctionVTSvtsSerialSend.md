[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSerialSend.md)

**CAPL Functions** » **VT System** » **vtsSerialSend**

# vtsSerialSend

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long vtsSerialSend (char Target[], byte buffer[], dword number);
```

## Description

Sends a block of bytes to the serial port of the specified VT7001 channel

- The operation starts the sending of a block.
- A callback handler can be set to notify when the send operation is completed. See [SerialSetOnSendHandler](CAPLfunctionVTSSerialSetOnSendHandler.md).
- Another callback handler can be set to notify of errors in later stages of the send operation. See [SerialSetOnErrorHandler](CAPLfunctionVTSSerialSetOnErrorHandler.md). There are no automatic retrials in case of error.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **buffer**: An array of bytes that contains the data to be sent.
- **number**: Number of bytes to send from the buffer. Number must have a value > 0 and < 65.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: One of the parameters has an invalid value.
- **-5**: Serial port is not open.

## Example

See example [vtsSerialConfigure](CAPLfunctionVTSvtsSerialConfigure.md)

[SerialSend](CAPLfunctionVTSSerialSend.md)
