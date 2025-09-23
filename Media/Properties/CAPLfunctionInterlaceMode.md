# InterlaceMode

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Property

InterlaceMode

## Description

Describes how the frames in a video media type are interlaced.

## Data Type

dword

## Remarks

The value of this property is one of the following:

- VideoInterlace_Unknown = 0,
- VideoInterlace_Progressive = 2,
- VideoInterlace_FieldInterleavedUpperFirst = 3,
- VideoInterlace_FieldInterleavedLowerFirst = 4,
- VideoInterlace_FieldSingleUpper = 5,
- VideoInterlace_FieldSingleLower = 6,
- VideoInterlace_MixedInterlaceOrProgressive = 7,
- VideoInterlace_Last, MFVideoInterlace_ForceDWORD = 0x7FFFFFFF
