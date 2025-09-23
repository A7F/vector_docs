# FrameRate

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Property

FrameRate

## Description

Frame rate of a video media type, in frames per second.

## Data Type

qword

## Remarks

The frame rate is expressed as a ratio. The upper 32 bits of the property value contain the numerator and the lower 32 bits contain the denominator. For example, if the frame rate is 30 frames per second (fps), the ratio is 30/1. If the frame rate is 29.97 fps, the ratio is 30,000/1001.

To set the value, use the [MediaSetPropertyRatio](../Functions/CAPLfunctionMediaSetPropertyRatio.md) function.

To get the value, use the [MediaGetPropertyRatio](../Functions/CAPLfunctionMediaGetPropertyRatio.md) function.

[See Also](javascript:void(0);)
