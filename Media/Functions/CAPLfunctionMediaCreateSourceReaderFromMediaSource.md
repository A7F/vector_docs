# MediaCreateSourceReaderFromMediaSource

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword MediaCreateSourceReaderFromMediaSource(dword mediaSourceHandle);
```

## Description

Creates the source reader from a media source.

For more information regarding the source reader see [source reader](../CAPLfunctionsMediaSouceReader.md).

## Parameters

- **mediaSourceHandle**: The media source to create the source reader from. This is the handle returned by the [MediaCreateAudioCapturer](CAPLfunctionMediaCreateAudioCapturer.md) function.

## Return Values

- **0**: The function failed. Call [MediaGetLastError](CAPLfunctionMediaGetLastError.md) to get a more specific error code.
- **≠0**: Source reader handle

## Example

—

[See Also](javascript:void(0);)
