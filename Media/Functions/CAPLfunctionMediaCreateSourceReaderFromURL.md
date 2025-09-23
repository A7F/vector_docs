# MediaCreateSourceReaderFromURL

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword MediaCreateSourceReaderFromURL(char mediaFileUrl[]);
```

## Description

Creates the source reader from a URL. For more information regarding the source reader see [source reader](../CAPLfunctionsMediaSouceReader.md).

## Parameters

- **mediaFileUrl**: The URL of a media file to open. For a list of supported media formats in files see [supported media formats](../CAPLfunctionsMediaFormats.md).

## Return Values

- **0**: The function failed. Call [MediaGetLastError](CAPLfunctionMediaGetLastError.md) to get a more specific error code.
- **≠0**: Source reader handle

## Example

—

[See Also](javascript:void(0);)

- MediaCreateAudioCapturer
- MediaCreateAudioRenderer
- MediaCreateMediaType
- MediaCreateSinkWriterFromMediaSink
- MediaCreateSinkWriterFromURL
- MediaCreateSourceReaderFromMediaSource
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
