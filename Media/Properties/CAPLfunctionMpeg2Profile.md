[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionMpeg2Profile.md)

**CAPL Functions** » **Media API** » **Properties** » **Mpeg2Profile**

# Mpeg2Profile

**Valid for**: CANoe DE • CANoe4SW DE

## Property

Mpeg2Profile

## Description

Specifies the MPEG-2 or H.264 profile in a video media type.

## Data Type

dword

## Remarks

For MPEG-2 video, the value of this property is one of the following:

- AM_MPEG2Profile_Simple = 1,
- AM_MPEG2Profile_Main = 2,
- AM_MPEG2Profile_SNRScalable = 3,
- AM_MPEG2Profile_SpatiallyScalable = 4,
- AM_MPEG2Profile_High = 5

DVD video decoders should support **MPEG2Profile_Simple** or **MPEG2Profile_Main**.

For H.264 video, the value of this property is one of the following:

- eAVEncH264VProfile_unknown = 0,
- eAVEncH264VProfile_Simple = 66,
- eAVEncH264VProfile_Base = 66,
- eAVEncH264VProfile_Main = 77,
- eAVEncH264VProfile_High = 100,
- eAVEncH264VProfile_422 = 122,
- eAVEncH264VProfile_High10 = 110,
- eAVEncH264VProfile_444 = 144,
- eAVEncH264VProfile_Extended = 88,
- eAVEncH264VProfile_ScalableBase = 83,
- eAVEncH264VProfile_ScalableHigh = 86,
- eAVEncH264VProfile_MultiviewHigh = 118,
- eAVEncH264VProfile_StereoHigh = 128,
- eAVEncH264VProfile_ConstrainedBase = 256,
- eAVEncH264VProfile_UCConstrainedHigh = 257,
- eAVEncH264VProfile_UCScalableConstrainedBase = 258,
- eAVEncH264VProfile_UCScalableConstrainedHigh = 259

These values are used with the **MpegProfile** property.

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)