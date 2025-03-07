[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/CAPLfunctionsMediaSinkWriter.md)

**CAPL Functions** » [Media AP](CAPLfunctionsMediaOverview.md) » [Media Concepts](CAPLfunctionsMediaConcept.md) » Media Sink Writer

# Media Sink Writer

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

The sink writer is a component for encoding audio or video files.

The following diagram shows, at a high level, how an application uses the sink writer to encode and audio/video file.

The sink writer hosts a media sink and optionally one or more encoders. The encoders convert uncompressed audio or video data to encoded bitstreams. The media sink outputs the bitstreams to a file. The sink writer performs the following tasks:

- Loads the media sink.
- Finds and loads the encoders.
- Manages the data flow to the encoders and the media sink.

The application passes audio/video data to the sink writer as input. It does not matter how the application obtains or generates the input data. One option is to use the source reader. However, the sink writer does not require the use of the source reader. These two components are independent.

[Media Concepts](CAPLfunctionsMediaConcept.md) • [Media Formats](CAPLfunctionsMediaFormats.md) • [Source Reader](CAPLfunctionsMediaSouceReader.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)