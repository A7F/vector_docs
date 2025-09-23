# MediaCreateAudioRenderer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword MediaCreateAudioRenderer();
```

## Description

Creates the streaming audio renderer (SAR) which is a media sink that renders audio in an output device, e.g. a headphone or speaker. Each instance of the SAR renders a single audio stream. To render multiple streams, use multiple instances of the SAR.

The SAR can receive uncompressed audio in either PCM or IEEE floating-point format.

## Parameters

—

## Return Values

- **0**: The function failed. Call [MediaGetLastError](CAPLfunctionMediaGetLastError.md) to get a more specific error code.
- **≠0**: Audio renderer handle

## Example

—
