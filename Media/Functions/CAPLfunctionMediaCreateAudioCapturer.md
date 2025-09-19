[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaCreateAudioCapturer.md)

**CAPL Functions** » [Media API](../CAPLfunctionsMediaOverview.md) » MediaCreateAudioCapturer

# MediaCreateAudioCapturer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword MediaCreateAudioCapturer();
```

## Description

Creates a streaming audio capturer which is a media source that captures audio from an input device, e.g. a microphone.

The audio capturer provides uncompressed audio in either PCM or IEEE floating-point format.

## Parameters

—

## Return Values

- **0**: The function failed. Call [MediaGetLastError](CAPLfunctionMediaGetLastError.md) to get a more specific error code.
- **≠0**: Audio capturer handle

## Example

—

[See Also](javascript:void(0);)
