[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionOriginal4cc.md)

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » [Properties](../CAPLfunctionsMediaProperties.md) » Original4cc

# Original4cc

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

Original4cc

## Description

Contains the original codec FOURCC for a video stream.

## Data Type

dword

## Remarks

- Depending on the source file, the AVI media source might set this property on the media types that it offers.
- An AVI file contains a stream header for each stream in the file. The AVI media source translates the stream header into a media type. For compressed video streams, the stream header contains a FOURCC that identifies the video codec. In most cases, the AVI media source converts this FOURCC directly to a subtype, see [Video Subtypes](../CAPLfunctionsMediaMajorMediaTypesSubtypes.md). In some cases, however, it maps the original FOURCC to another FOURCC that is equivalent. If so, the media source stores the original FOURCC in the media type, using the **Original4cc** property.
- The FOURCC mappings are stored in the Registry under the following key:

  `HKEY_CLASSES_ROOT\MediaFoundation\MapVideo4cc`

- Each entry is a dword value. The name of the entry is the hexadecimal representation of the FOURCC, without an `0x` prefix, and with the first character appearing first in the string. For example, the FOURCC code **abcd** would appear as **61626364**. The value of the entry is the equivalent FOURCC code.

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
