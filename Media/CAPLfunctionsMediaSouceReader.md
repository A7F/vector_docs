[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/CAPLfunctionsMediaSouceReader.md)

[CAPL Functions](../CAPLfunctions.md) » [Media AP](CAPLfunctionsMediaOverview.md) » [Media Concepts](CAPLfunctionsMediaConcept.md) » Media Source Reader

# Media Source Reader

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

Internally, the source reader references a media source. A media source is an object that generates media data from an external source, such as a media file or video capture device. The source reader manages all of the method calls to the media source.

If the media source delivers compressed data, you can use the source reader to decode the data. In that case, the source reader will load the correct decoder and manage the data flow between the media source and the decoder.

The source reader does not send the data to a destination; it is up to the application to consume the data. For example, the source reader can read a video file, but it will not render the video to the screen.

Consider using the source reader when:

- You want to get data from a media file without worrying about the underlying file structure.
- You want to get data from an audio or video capture device.

The source reader is not recommended in the following situations:

- For protected content. The source reader does not support digital rights management (DRM).
- If you care about the details of the underlying file structure. The source reader hides that type of detail.

[Media Concepts](CAPLfunctionsMediaConcept.md) • [Media Formats](CAPLfunctionsMediaFormats.md) • [Sink Writer](CAPLfunctionsMediaSinkWriter.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)