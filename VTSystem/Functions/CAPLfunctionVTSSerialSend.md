[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSerialSend.md)

**CAPL Functions** » **VT System** » **SerialSend**

# SerialSend

**Valid for**: CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of channels that represent an external power supply in a power module **VT7001** respectively the system variable namespace that represents functionality common for the entire **VT7001** module.

## Method Syntax

`long SysVarNamespace.SerialSend( byte buffer[], dword number);`

## Description

Sends a block of bytes to the serial port of the specified **VT7001** channel

- The operation starts the sending of a block.
- A callback handler can be set to notify when the send operation is completed. See [SerialSetOnSendHandler](CAPLfunctionVTSSerialSetOnSendHandler.md).
- Another callback handler can be set to notify of errors in later stages of the send operation. See [SerialSetOnErrorHandler](CAPLfunctionVTSSerialSetOnErrorHandler.md). There are no automatic retrials in case of error.

## Parameters

- **buffer**: An array of bytes that contains the data to be sent.
- **number**: Number of bytes to send from the buffer. Number must have a value > 0 and < 65.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: One of the parameters has an invalid value.
- **-5**: Serial port is not open.

## Example

See example [SerialConfigure](CAPLfunctionVTSSerialConfigure.md)

[vtsSerialSend](CAPLfunctionVTSvtsSerialSend.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
