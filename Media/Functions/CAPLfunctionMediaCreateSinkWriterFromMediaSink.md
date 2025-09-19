[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaCreateSinkWriterFromMediaSink.md)

**CAPL Functions** » **Media API** » **MediaCreateSinkWriterFromMediaSink**

# MediaCreateSinkWriterFromMediaSink

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword MediaCreateSinkWriterFromMediaSink(dword mediaSinkHandle);
```

## Description

Creates the source reader from a media source.

For more information regarding the source reader see [source reader](../CAPLfunctionsMediaSouceReader.md).

## Parameters

- **mediaFileHandle**: The media sink to create the sink writer from. This is the handle returned by the [MediaCreateAudioRenderer](CAPLfunctionMediaCreateAudioRenderer.md) function.

## Return Values

- **0**: The function failed. Call [MediaGetLastError](CAPLfunctionMediaGetLastError.md) to get a more specific error code.
- **≠0**: Sink writer handle.

## Example

—

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
