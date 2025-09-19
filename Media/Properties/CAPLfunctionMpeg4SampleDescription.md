[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionMpeg4SampleDescription.md)

**CAPL Functions** » **Media API** » **Properties** » **Mpeg4SampleDescription**

# Mpeg4SampleDescription

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

Mpeg4SampleDescription

## Description

Contains the sample description box for an MP4 or 3GP file.

## Data Type

byte[]

## Remarks

- The sample description box describes the encoding used for a stream in the file.
- The MPEG-4 file source sets this attribute on the media type for each stream. The value of the property is the raw data in the sample description box. If the MPEG-4 file source can parse the sample description, it also adds the format details to the media type. Otherwise, the application or the decoder must parse the sample description from the **Mpeg4SampleDescription** property.
- When setting this property on a sink writer accessing a MPEG-4 sink through the [MediaSetMediaType](../Functions/CAPLfunctionMediaSetMediaType.md) function, the data for the property **Mpeg4SampleDescription** should not change after one or more samples have been sent to the sink writer via the [MediaWrite](../Functions/CAPLfunctionMediaWrite.md) function.

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
