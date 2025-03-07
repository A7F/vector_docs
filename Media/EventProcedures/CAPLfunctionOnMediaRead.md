[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/EventProcedures/CAPLfunctionOnMediaRead.md)

## CAPL Functions » Media API » OnMediaRead

### OnMediaRead

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Function Syntax

```c
void OnMediaRead(dword sourceReaderHandle, long result, dword streamIndex, dword streamFlags, int64 timestamp, byte buffer[], dword length);
void OnMediaRead(dword sourceReaderHandle, long result, dword streamIndex, dword streamFlags, int64 timestamp, int buffer[], dword length);
void OnMediaRead(dword sourceReaderHandle, long result, dword streamIndex, dword streamFlags, int64 timestamp, long buffer[], dword length);
```

### Description

This callback is dispatched when an asynchronous read operation on a source reader completes.

### Parameters

- **sourceReaderHandle**: The source reader handle.
- **result**: The specific result code of the operation. If the operation completed successfully the value is zero. Otherwise the value is non-zero.
- **streamIndex**: The zero-based index of the stream that delivered the sample.
- **streamFlags**: 
  - **SOURCE_READERF_ERROR (0x00000001)**: An error occurred. If you receive this flag, do not make any further calls to [SourceReader](../CAPLfunctionsMediaSouceReader.md) methods.
  - **SOURCE_READERF_ENDOFSTREAM (0x00000002)**: The source reader reached the end of the stream.
  - **SOURCE_READERF_NEWSTREAM (0x00000004)**: One or more new streams were created. Respond to this flag by doing at least one of the following:
    - Set the output types on the new streams.
    - Update the stream selection by selecting or deselecting streams.
  - **SOURCE_READERF_NATIVEMEDIATYPECHANGED (0x00000010)**: The native format has changed for one or more streams. The native format is the format delivered by the media source before any decoders are inserted.
  - **SOURCE_READERF_CURRENTMEDIATYPECHANGED (0x00000020)**: The current media has type changed for one or more streams. To get the current media type, call the source reader’s [GetMediaType](../Functions/CAPLfunctionMediaGetMediaType.md) method.
  - **MF_SOURCE_READERF_STREAMTICK (0x00000100)**: There is a gap in the stream.
  - **SOURCE_READERF_ALLEFFECTSREMOVED (0x00000200)**: All transforms inserted by the application have been removed for a particular stream. This could be due to a dynamic format change from a source or decoder that prevents custom transforms from being used because they cannot handle the new media type.
- **buffer**: The buffer into which the data was stored.
- **length**: The length of the received data.

### Return Values

—

### Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)