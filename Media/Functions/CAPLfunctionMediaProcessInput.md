[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaProcessInput.md)

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » MediaProcessInput

# MediaProcessInput

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long MediaProcessInput(dword de-/multiplexerHandle, dword inputStreamIndex, int64 timestamp, byte buffer[], dword length)
```

## Description

Delivers data to an input stream on this de-/multiplexer.

## Parameters

- **de-/multiplexerHandle**: The de-/multiplexer handle returned previously by a call to [MediaCreateMultiplexer](CAPLfunctionMediaCreateMultiplexer.md)/[MediaCreateDemultiplexer](CAPLfunctionMediaCreateDemultiplexer.md).
- **inputStreamIndex**: The index of the input stream the media type should be set for. Currently only 1 input stream per multiplex stream is supported, so set this parameter to 0. For demultiplexers set to 0.
- **timestamp**: The (presentation) timestamp in nanoseconds. This time is relative to the start of the stream (not the absolute gPTP time).
- **buffer**: The sample data for the input stream that should be processed.
- **length**: The length of the sample data in the buffer array in bytes.

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md).

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
