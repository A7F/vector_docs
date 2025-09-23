# YuvMatrix

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

YuvMatrix

## Description

For YUV media types, defines the conversion matrix from the Y'Cb'Cr' color space to the R'G'B' color space.

## Data Type

dword

## Remarks

The value of this property is one of the following:

- VideoTransferMatrix_Unknown = 0,
- VideoTransferMatrix_BT709 = 1,
- VideoTransferMatrix_BT601 = 2,
- VideoTransferMatrix_SMPTE240M = 3,
- VideoTransferMatrix_Last, MFVideoTransferMatrix_ForceDWORD = 0x7FFFFFFF

[See Also](javascript:void(0);)
