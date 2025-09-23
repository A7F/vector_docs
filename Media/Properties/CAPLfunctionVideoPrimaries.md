# VideoPrimaries

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Property

VideoPrimaries

## Description

Specifies the color primaries for a video media type.

## Data Type

dword

## Remarks

The value of this property is one of the following:

- VideoPrimaries_Unknown = 0,
- VideoPrimaries_reserved = 1,
- VideoPrimaries_BT709 = 2,
- VideoPrimaries_BT470_2_SysM = 3,
- VideoPrimaries_BT470_2_SysBG = 4,
- VideoPrimaries_SMPTE170M = 5,
- VideoPrimaries_SMPTE240M = 6,
- VideoPrimaries_EBU3213 = 7,
- VideoPrimaries_SMPTE_C = 8,
- VideoPrimaries_BT2020 = 9,
- VideoPrimaries_XYZ = 10,
- VideoPrimaries_DCI_P3 = 11,
- VideoPrimaries_ACES = 12,
- VideoPrimaries_Last, MFVideoPrimaries_ForceDWORD = 0x7FFFFFFF

The values identify color primaries associated with certain common video standards.

If the media type uses color primaries that are not identified by the above values, set the `CustomVideoPrimaries` property instead of this property.

[See Also](javascript:void(0);)

- [AvgBitErrorRate](CAPLfunctionAvgBitErrorRate.md#aanchor23847)
- [AvgBitrate](CAPLfunctionAvgBitrate.md#aanchor26980)
- [DefaultStride](CAPLfunctionDefaultStride.md#aanchor12043)
- [DrmFlags](CAPLfunctionDrmFlags.md#aanchor366)
- [FrameRate](CAPLfunctionFrameRate.md#aanchor16466)
- [FrameRateRangeMax](CAPLfunctionFrameRateRangeMax.md#aanchor20450)
- [FrameRateRangeMin](CAPLfunctionFrameRateRangeMin.md#aanchor21081)
- [FrameSize](CAPLfunctionFrameSize.md#aanchor28634)
- [GeometricAperture](CAPLfunctionGeometricAperture.md#aanchor3703)
- [InterlaceMode](CAPLfunctionInterlaceMode.md#aanchor16382)
- [MaxKeyframeSpacing](CAPLfunctionMaxKeyframeSpacing.md#aanchor22056)
- [Media Properties](../CAPLfunctionsMediaProperties.md#aanchor20862)
- [MinimumDisplayAperture](CAPLfunctionMinimumDisplayAperture.md#aanchor17628)
- [Mpeg2Flags](CAPLfunctionMpeg2Flags.md#aanchor2140)
- [Mpeg2Level](CAPLfunctionMpeg2Level.md#aanchor18663)
- [Mpeg2Profile](CAPLfunctionMpeg2Profile.md#aanchor8044)
- [MpegSequenceHeader](CAPLfunctionMpegSequenceHeader.md#aanchor3866)
- [MpegStartTimeCode](CAPLfunctionMpegStartTimeCode.md#aanchor11934)
- [Original4cc](CAPLfunctionOriginal4cc.md#aanchor16483)
- [PadControlFlags](CAPLfunctionPadControlFlags.md#aanchor23275)
- [Palette](CAPLfunctionPalette.md#aanchor21899)
- [PanScanAperture](CAPLfunctionPanScanAperture.md#aanchor9603)
- [PanScanEnabled](CAPLfunctionPanScanEnabled.md#aanchor21064)
- [PixelAspectRatio](CAPLfunctionPixelAspectRatio.md#aanchor17346)
- [SourceContentHint](CAPLfunctionSourceContentHint.md#aanchor25185)
- [TransferFunction](CAPLfunctionTransferFunction.md#aanchor7282)
- [Video3d](CAPLfunctionVideo3d.md#aanchor30214)
- [VideoChromaSiting](CAPLfunctionVideoChromaSiting.md#aanchor27572)
- [VideoLighting](CAPLfunctionVideoLighting.md#aanchor30228)
- [VideoNominalRange](CAPLfunctionVideoNominalRange.md#aanchor25937)
- [VideoPrimaries](#aanchor17253)
- [VideoRotation](CAPLfunctionVideoRotation.md#aanchor20469)
- [YuvMatrix](CAPLfunctionYuvMatrix.md#aanchor18492)
