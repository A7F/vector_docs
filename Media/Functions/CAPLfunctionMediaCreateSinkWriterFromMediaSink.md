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
