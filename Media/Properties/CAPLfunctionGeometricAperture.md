[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionGeometricAperture.md)

**CAPL Functions** » [Media API](../CAPLfunctionsMediaOverview.md) » [Properties](../CAPLfunctionsMediaProperties.md) » GeometricAperture

# GeometricAperture

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

GeometricAperture

## Description

Defines the geometric aperture for a video media type.

## Data Type

dword

## Remarks

The picture aspect ratio is calculated relative to the geometric aperture, using the following formula: Picture aspect ratio = (geometric aperture width / geometric aperture height) × pixel aspect ratio.

If this property is not set, the geometric aperture is assumed to be the entire video frame. You should set this property only when the media type describes a video standard with a defined active area.

For example, in NTSC television the video frame is 720 × 480 with an active area of 704 × 480 and a 10:11 pixel aspect ratio. The resulting picture has an aspect ratio of (704/480) × (10/11) = 4:3.

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)