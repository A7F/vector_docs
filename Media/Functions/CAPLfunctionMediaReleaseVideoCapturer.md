[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaReleaseVideoCapturer.md)

**CAPL Functions** » [Media API](../CAPLfunctionsMediaOverview.md) » MediaReleaseVideoCapturer

# MediaReleaseVideoCapturer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword MediaReleaseVideoCapturer(dword videoCapturerHandle);
```

## Description

Releases the video capturer.

## Parameters

- **videoCapturerHandles**: The video capturer handle.

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)

- [MediaCreateAudioCapturer](CAPLfunctionMediaCreateAudioCapturer.md#aanchor9056)
- [MediaCreateAudioRenderer](CAPLfunctionMediaCreateAudioRenderer.md#aanchor10699)
- [MediaCreateMediaType](CAPLfunctionMediaCreateMediaType.md#aanchor17471)
- [MediaCreateSinkWriterFromMediaSink](CAPLfunctionMediaCreateSinkWriterFromMediaSink.md#aanchor21097)
- [MediaCreateSinkWriterFromURL](CAPLfunctionMediaCreateSinkWriterFromURL.md#aanchor7048)
- [MediaCreateSourceReaderFromMediaSource](CAPLfunctionMediaCreateSourceReaderFromMediaSource.md#aanchor20192)
- [MediaCreateSourceReaderFromURL](CAPLfunctionMediaCreateSourceReaderFromURL.md#aanchor14837)
- [MediaEnumAudioCapturers](CAPLfunctionMediaEnumAudioCapturers.md#aanchor23537)
- [MediaEnumVideoCapturers](CAPLfunctionMediaEnumVideoCapturers.md#aanchor29408)
- [MediaGetLastError](CAPLfunctionMediaGetLastError.md#aanchor22441)
- [MediaGetMediaType](CAPLfunctionMediaGetMediaType.md#aanchor13256)
- [MediaGetProperty](CAPLfunctionMediaGetProperty.md#aanchor25863)
- [MediaGetPropertyRatio](CAPLfunctionMediaGetPropertyRatio.md#aanchor30101)
- [MediaGetPropertySize](CAPLfunctionMediaGetPropertySize.md#aanchor30125)
- [MediaRead](CAPLfunctionMediaRead.md#aanchor24108)
- [MediaReleaseAudioCapturer](CAPLfunctionMediaReleaseAudioCapturer.md#aanchor24212)
- [MediaReleaseAudioRenderer](CAPLfunctionMediaReleaseAudioRenderer.md#aanchor15253)
- [MediaReleaseMediaType](CAPLfunctionMediaReleaseMediaType.md#aanchor31904)
- [MediaReleaseSinkWriter](CAPLfunctionMediaReleaseSinkWriter.md#aanchor4777)
- [MediaReleaseSourceReader](CAPLfunctionMediaReleaseSourceReader.md#aanchor28029)
- [MediaReleaseVideoCapturer](#aanchor15102)
- [MediaSetMediaType](CAPLfunctionMediaSetMediaType.md#aanchor30942)
- [MediaSetProperty](CAPLfunctionMediaSetProperty.md#aanchor14831)
- [MediaSetPropertyRatio](CAPLfunctionMediaSetPropertyRatio.md#aanchor7541)
- [MediaSetPropertySize](CAPLfunctionMediaSetPropertySize.md#aanchor9917)
- [MediaWrite](CAPLfunctionMediaWrite.md#aanchor16167)
- [OnMediaRead](../EventProcedures/CAPLfunctionOnMediaRead.md#aanchor21142)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
