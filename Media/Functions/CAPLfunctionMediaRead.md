[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaRead.md)

**CAPL Functions** » **Media API** » **MediaRead**

# MediaRead

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaRead(dword sourceReaderHandle, dword streamIndex, byte buffer[], dword length, char onReadCallback[]);
long MediaRead(dword sourceReaderHandle, dword streamIndex, int buffer[], dword length, char onReadCallback[]);
long MediaRead(dword sourceReaderHandle, dword streamIndex, long buffer[], dword length, char onReadCallback[]);
```

## Description

Reads sample data from the media source.

## Parameters

- **sourceReaderHandle**: The source reader handle.
- **streamIndex**: The stream to pull data from. The value can be:
  - `0–0xFFFFFFFB`: The zero-based index of a stream.
  - **SOURCE_READER_FIRST_VIDEO_STREAM**: `0xFFFFFFFC` - The first video stream.
  - **SOURCE_READER_FIRST_AUDIO_STREAM**: `0xFFFFFFFD` - The first audio stream.
  - **SOURCE_READER_ANY_STREAM**: `0xFFFFFFFE` - Get the next available sample, regardless of which stream.
- **buffer**: The buffer used to store the incoming data.
- **length**: The length of the data buffer.
- **onReadCallback**: The name of the CAPL callback function (see [OnMediaRead](../EventProcedures/CAPLfunctionOnMediaRead.md)).

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)