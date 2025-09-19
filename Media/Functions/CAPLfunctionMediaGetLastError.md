[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaGetLastError.md)

**CAPL Functions » Media API » MediaGetLastError**

# MediaGetLastError

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword MediaGetLastError();
```

## Description

Retrieves the calling CAPL program’s last-error code value of the Media API. This code represents a Windows HRESUL value typically in the value ranges reserved for the Windows Media Foundation (see [error codes](../CAPLfunctionsMediaErrorCodes.md)).

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

```plaintext
dword retVal;
dword listenerHandle;
// open a listener
listenerHandle = AvbOpenListener();

// check if last function was successfully executed
if ((retVal = AvbGetLastError()) != 0)
{
  write("AVB IL error occured: Error code: %d", retVal);
}
```

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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
