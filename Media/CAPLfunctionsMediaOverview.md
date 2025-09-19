[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/CAPLfunctionsMediaOverview.md)

[CAPL Functions](../CAPLfunctions.md) » Media CAPL Functions

# Media CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Media**

- Only available with Option Ethernet.
- To use the CAPL functions the [AVB_IL.vmodule](../../CANoeCANalyzer/Ethernet/ILAVB/ILAVBInclude.md) must be included.

---

**ON THIS PAGE:**

- [Further Topics](#BMFurtherTopics)
- [Callbacks](#Callbacks)
- [General Functions](#General)
- [Media Sink Functions](#MediaSink)
- [Media Source Functions](#MediaSource)
- [Media Type Functions](#MediaType)
- [Multiplexer/Demultiplexer](#Multiplexer)
- [Sink Writer Functions](#SinkWriter)
- [Source Reader/Sink Writer Functions](#ReaderWriter)
- [Source Reader Functions](#SourceReader)

## Callbacks 

- **[OnMediaRead](EventProcedures/CAPLfunctionOnMediaRead.md)**: This callback is dispatched when an asynchronous read operation on a source reader completes.

## General Functions 

- **[MediaGetLastError](Functions/CAPLfunctionMediaGetLastError.md)**: Retrieves the calling CAPL program’s last-error code value of the Media API.
- **[MediaGetProperty](Functions/CAPLfunctionMediaGetProperty.md)**: Gets the properties used for configuring the behavior of an object.
- **[MediaSetProperty](Functions/CAPLfunctionMediaSetProperty.md)**: Sets the properties used for configuring the behavior of an object.
- **[MediaGetPropertyRatio](Functions/CAPLfunctionMediaGetPropertyRatio.md)**: Retrieves a property whose value is a ratio.
- **[MediaSetPropertyRatio](Functions/CAPLfunctionMediaSetPropertyRatio.md)**: Sets a ratio as a 64-bit property value.
- **[MediaGetPropertySize](Functions/CAPLfunctionMediaGetPropertySize.md)**: Retrieves a property whose value is a size, expressed as a width and height.
- **[MediaSetPropertySize](Functions/CAPLfunctionMediaSetPropertySize.md)**: Sets width and height as a single 64-bit property value.

## Media Sink Functions 

- **[MediaCreateAudioRenderer](Functions/CAPLfunctionMediaCreateAudioRenderer.md)**: Creates the streaming audio renderer (SAR) which is a media sink that renders audio in an output device.
- **[MediaReleaseAudioRenderer](Functions/CAPLfunctionMediaReleaseAudioRenderer.md)**: Releases the audio renderer.

## Media Source Functions 

- **[MediaCreateAudioCapturer](Functions/CAPLfunctionMediaCreateAudioCapturer.md)**: Creates a streaming audio capturer which is a media source that captures audio from an input device.
- **[MediaEnumAudioCapturers](Functions/CAPLfunctionMediaEnumAudioCapturers.md)**: Enumerates a list of audio capture devices.
- **[MediaReleaseAudioCapturer](Functions/CAPLfunctionMediaReleaseAudioCapturer.md)**: Releases the audio capturer.
- **[MediaEnumVideoCapturers](Functions/CAPLfunctionMediaEnumVideoCapturers.md)**: Enumerates a list of video capture devices.
- **[MediaReleaseVideoCapturer](Functions/CAPLfunctionMediaReleaseVideoCapturer.md)**: Releases the video capturer.

## Media Type Functions 

- **[MediaReleaseMediaType](Functions/CAPLfunctionMediaReleaseMediaType.md)**: Releases a media type retrieved by [MediaGetMediaType](Functions/CAPLfunctionMediaGetMediaType.md).
- **[MediaCreateMediaType](Functions/CAPLfunctionMediaCreateMediaType.md)**: Creates an empty media type.

## Multiplexer/Demultiplexer 

- **[MediaCreateDemultiplexer](Functions/CAPLfunctionMediaCreateDemultiplexer.md)**: Creates a demultiplexer for the provided input media subtype.
- **[MediaCreateMultiplexer](Functions/CAPLfunctionMediaCreateMultiplexer.md)**: Creates a multiplexor for the provided output media subtype.
- **[MediaGetInputType](Functions/CAPLfunctionMediaGetInputType.md)**: Retrieves the media type of a stream the de-/multiplexer takes as input.
- **[MediaGetOutputType](Functions/CAPLfunctionMediaGetOutputType.md)**: Retrieves the media type of a stream the de-/multiplexer produces as output (at a given index).
- **[MediaProcessInput](Functions/CAPLfunctionMediaProcessInput.md)**: Delivers data to an input stream on this de-/multiplexer.
- **[MediaProcessOutput](Functions/CAPLfunctionMediaProcessOutput.md)**: Generates output from the current input data.
- **[MediaReleaseDemultiplexer](Functions/CAPLfunctionMediaReleaseDemultiplexer.md)**: Releases a demultiplexer.
- **[MediaReleaseMultiplexer](Functions/CAPLfunctionMediaReleaseMultiplexer.md)**: Releases a multiplexer.
- **[MediaSetInputType](Functions/CAPLfunctionMediaSetInputType.md)**: Sets the input media type for a de-/multiplexer (at a given index).

## Sink Writer Functions 

- **[MediaCreateSinkWriterFromMediaSink](Functions/CAPLfunctionMediaCreateSinkWriterFromMediaSink.md)**: Creates the source reader from a media source.
- **[MediaCreateSinkWriterFromURL](Functions/CAPLfunctionMediaCreateSinkWriterFromURL.md)**: Creates the sink writer from a URL.
- **[MediaReleaseSinkWriter](Functions/CAPLfunctionMediaReleaseSinkWriter.md)**: Releases the sink writer.
- **[MediaWrite](Functions/CAPLfunctionMediaWrite.md)**: Delivers sample data to the sink writer.

## Source Reader/Sink Writer Functions 

- **[MediaGetMediaType](Functions/CAPLfunctionMediaGetMediaType.md)**: Gets the media type for a source reader.
- **[MediaSetMediaType](Functions/CAPLfunctionMediaSetMediaType.md)**: Sets the media type for a source reader or a sink writer.

## Source Reader Functions 

- **[MediaCreateSourceReaderFromMediaSource](Functions/CAPLfunctionMediaCreateSourceReaderFromMediaSource.md)**: Creates the source reader from a media source.
- **[MediaCreateSourceReaderFromURL](Functions/CAPLfunctionMediaCreateSourceReaderFromURL.md)**: Creates the source reader from a URL.
- **[MediaRead](Functions/CAPLfunctionMediaRead.md)**: Reads sample data from the media source.
- **[MediaReleaseSourceReader](Functions/CAPLfunctionMediaReleaseSourceReader.md)**: Releases the source reader.

[Media Concepts](CAPLfunctionsMediaConcept.md) • [Media Properties](CAPLfunctionsMediaProperties.md) • [Major Media Types / Audio Subtypes](CAPLfunctionsMediaMajorMediaTypesSubtypes.md) • [Error Codes](CAPLfunctionsMediaErrorCodes.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
