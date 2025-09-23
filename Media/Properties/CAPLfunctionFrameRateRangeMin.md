# FrameRateRangeMin

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Property

FrameRateRangeMin

## Description

The minimum frame rate that is supported by a video capture device, in frames per second.

## Data Type

qword

## Remarks

- To get this property, call [MediaGetPropertyRatio](../Functions/CAPLfunctionMediaGetPropertyRatio.md).
- To set this property, call [MediaSetPropertyRatio](../Functions/CAPLfunctionMediaSetPropertyRatio.md).
- The frame rate is expressed as a ratio. The upper 32 bits of the property value contain the numerator, and the lower 32 bits contain the denominator. For example, if the frame rate is 30 frames per second (fps), the ratio is 30/1.
- If the capture device reports a minimum frame rate, the media source sets this property on the media type. The maximum frame rate is given in the [FrameRateRangeMax](CAPLfunctionFrameRateRangeMax.md) property. The device is not guaranteed to support every increment within this range.
- To set the device's frame rate, first modify the value of the [FrameRate](CAPLfunctionFrameRate.md) property on the media type. Then set the media type on the media source.
