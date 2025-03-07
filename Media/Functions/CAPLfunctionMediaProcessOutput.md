[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaProcessOutput.md)

## MediaProcessOutput

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » MediaProcessOutput

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long MediaProcessOutput(dword de-/multiplexerHandle, dword outputStreamIndex, int64& retTimestamp, byte buffer[], dword& length, dword& retStatus)
```

### Description

Generates output from the current input data.

### Parameters

- **de-/multiplexerHandle**: The de-/multiplexer handle returned previously by a call to [MediaCreateMultiplexer](CAPLfunctionMediaCreateMultiplexer.md)/[MediaCreateDemultiplexer](CAPLfunctionMediaCreateDemultiplexer.md).
- **outputStreamIndex**: The index of the output stream the media type should be retrieved for. For multiplexers set to 0.
- **retTimestamp**: The (presentation) timestamp in nanoseconds returned from this function. This time is relative to the start of the stream (not the absolute gPTP time).
- **buffer**: The sample data for the input stream that should be processed.
- **length**: In/Out parameter. Set to elCount(buffer) before calling this function. After the return of the function it contains the length of the sample data in the buffer array in bytes.
- **retStatus**: Before calling `MediaProcessOutput`, set this member to zero. When the method returns, the de-/multiplexer might set additional status flags. Otherwise, the de-/multiplexer leaves this member equal to zero.

### Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md).

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)