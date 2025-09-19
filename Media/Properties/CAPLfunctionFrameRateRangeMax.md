[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionFrameRateRangeMax.md)

**CAPL Functions** » **Media API** » **Properties** » **FrameRateRangeMax**

# FrameRateRangeMax

**Valid for**: CANoe DE • CANoe4SW DE

## Property

FrameRateRangeMax

## Description

The maximum frame rate that is supported by a video capture device, in frames per second.

## Data Type

qword

## Remarks

- To get this property, call [MediaGetPropertyRatio](../Functions/CAPLfunctionMediaGetPropertyRatio.md).
- To set this property, call [MediaSetPropertyRatio](../Functions/CAPLfunctionMediaSetPropertyRatio.md).
- The frame rate is expressed as a ratio. The upper 32 bits of the property value contain the numerator, and the lower 32 bits contain the denominator. For example, if the frame rate is 30 frames per second (fps), the ratio is 30/1.
- If the capture device reports a maximum frame rate, the media source sets this property on the media type. The minimum frame rate is given in the [FrameRateRangeMin](CAPLfunctionFrameRateRangeMin.md) property. The device is not guaranteed to support every increment within this range.
- To set the device's frame rate, first modify the value of the [FrameRate](CAPLfunctionFrameRate.md) property on the media type. Then set the media type on the media source.

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
