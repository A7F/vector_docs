# ImageLossTolerant

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

ImageLossTolerant

## Description

Specifies whether an ASF image stream is a degradable JPEG type.

## Data Type

dword

## Remarks

This property applies to the media type for image streams in ASF. If the value is **TRUE**, the stream is a degradable JPEG image type. Otherwise, the stream is a JFIF image type. For more information about these stream types, see the ASF specification.

In addition to the **ImageLossTolerant** property, the media type for an ASF image stream contains the properties [MajorType](CAPLfunctionMajorType.md) and [FrameSize](CAPLfunctionFrameSize.md).
