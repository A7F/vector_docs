# Mpeg2Level

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Property

Mpeg2Level

## Description

Specifies the MPEG-2 or H.264 level in a video media type.

## Data Type

dword

## Remarks

For MPEG-2 video, the value of this property is one of the following:

- AM_MPEG2Level_Low = 1,
- AM_MPEG2Level_Main = 2,
- AM_MPEG2Level_High1440 = 3,
- AM_MPEG2Level_High = 4

DVD MPEG-2 video decoders should support **AM_MPEG2Level_Low** or **AM_MPEG2Level_Main**.

For H.264 video, the value of this property is one of the following:

- eAVEncH264VLevel1 = 10,
- eAVEncH264VLevel1_b = 11,
- eAVEncH264VLevel1_1 = 11,
- eAVEncH264VLevel1_2 = 12,
- eAVEncH264VLevel1_3 = 13,
- eAVEncH264VLevel2 = 20,
- eAVEncH264VLevel2_1 = 21,
- eAVEncH264VLevel2_2 = 22,
- eAVEncH264VLevel3 = 30,
- eAVEncH264VLevel3_1 = 31,
- eAVEncH264VLevel3_2 = 32,
- eAVEncH264VLevel4 = 40,
- eAVEncH264VLevel4_1 = 41,
- eAVEncH264VLevel4_2 = 42,
- eAVEncH264VLevel5 = 50,
- eAVEncH264VLevel5_1 = 51,
- eAVEncH264VLevel5_2 = 51

These values are used with the **Mpeg2Level** property.

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
- [Mpeg2Level](#aanchor18663)
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
- [VideoPrimaries](CAPLfunctionVideoPrimaries.md#aanchor17253)
- [VideoRotation](CAPLfunctionVideoRotation.md#aanchor20469)
- [YuvMatrix](CAPLfunctionYuvMatrix.md#aanchor18492)
