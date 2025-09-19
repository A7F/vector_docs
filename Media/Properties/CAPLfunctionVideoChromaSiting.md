[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionVideoChromaSiting.md)

**CAPL Functions** » **Media API** » **Properties** » VideoChromaSiting

# VideoChromaSiting

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

VideoChromaSiting

## Description

Describes how chroma was sampled for a Y'Cb'Cr' video media type.

## Data Type

dword

## Remarks

The value of this property is one of the following:

- VideoChromaSubsampling_Unknown = 0,
- VideoChromaSubsampling_ProgressiveChroma = 0x8,
- VideoChromaSubsampling_Horizontally_Cosited = 0x4,
- VideoChromaSubsampling_Vertically_Cosited = 0x2,
- VideoChromaSubsampling_Vertically_AlignedChromaPlanes = 0x1,
- VideoChromaSubsampling_MPEG2 = VideoChromaSubsampling_Horizontally_Cosited | VideoChromaSubsampling_Vertically_AlignedChromaPlanes,
- VideoChromaSubsampling_MPEG1 = VideoChromaSubsampling_Vertically_AlignedChromaPlanes,
- VideoChromaSubsampling_DV_PAL = VideoChromaSubsampling_Horizontally_Cosited | VideoChromaSubsampling_Vertically_Cosited,
- VideoChromaSubsampling_Cosited = VideoChromaSubsampling_Horizontally_Cosited | VideoChromaSubsampling_Vertically_Cosited | VideoChromaSubsampling_Vertically_AlignedChromaPlanes,
- VideoChromaSubsampling_Las = MFVideoChromaSubsampling_Cosited + 1,
- VideoChromaSubsampling_ForceDWORD = 0x7FFFFFFF

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
