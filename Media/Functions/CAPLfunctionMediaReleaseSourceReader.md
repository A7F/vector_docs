# MediaReleaseSourceReader

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaReleaseSourceReader(dword sourceReaderHandle);
```

## Description

Releases the source reader.

## Parameters

- **sourceReaderHandle**: The source reader handle.

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)

- MediaCreateAudioCapturer
- MediaCreateAudioRenderer
- MediaCreateMediaType
- MediaCreateSinkWriterFromMediaSink
- MediaCreateSinkWriterFromURL
- MediaCreateSourceReaderFromMediaSource
- MediaCreateSourceReaderFromURL
- MediaEnumAudioCapturers
- MediaEnumVideoCapturers
- MediaGetLastError
- MediaGetMediaType
- MediaGetProperty
- MediaGetPropertyRatio
- MediaGetPropertySize
- MediaRead
- MediaReleaseAudioCapturer
- MediaReleaseAudioRenderer
- MediaReleaseMediaType
- MediaReleaseSinkWriter
- MediaReleaseSourceReader
- MediaReleaseVideoCapturer
- MediaSetMediaType
- MediaSetProperty
- MediaSetPropertyRatio
- MediaSetPropertySize
- MediaWrite
- OnMediaRead
