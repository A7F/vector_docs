[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaGetMediaType.md)

**CAPL Functions** » [Media API](../CAPLfunctionsMediaOverview.md) » MediaGetMediaType

# MediaGetMediaType

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaGetMediaType(dword sourceReaderHandle, dword streamIndex);
```

## Description

Gets the media type for a source reader.

## Parameters

- **sourceReaderHandle**: The source reader handle.
- **dwStreamIndex**: The stream to query. The value can be any of the following:
  - **0–0xFFFFFFFB**: The zero-based index of a stream.
  - **SOURCE_READER_FIRST_VIDEO_STREAM (0xFFFFFFFC)**: The first video stream.
  - **SOURCE_READER_FIRST_AUDIO_STREAM (0xFFFFFFFD)**: The first audio stream.

## Return Values

- **0**: The function failed. Call [MediaGetLastError](CAPLfunctionMediaGetLastError.md) to get a more specific error code.
- **≠0**: Media type handle

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)