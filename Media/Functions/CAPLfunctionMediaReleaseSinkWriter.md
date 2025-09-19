[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaReleaseSinkWriter.md)

**CAPL Functions** » **Media API** » **MediaReleaseSinkWriter**

# MediaReleaseSinkWriter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaReleaseSinkWriter(dword sinkWriterHandle);
```

## Description

Releases the sink writer.

## Parameters

- **sinkWriterHandle**: The sink writer handle.

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
