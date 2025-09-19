[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionFrameRate.md)

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » [Properties](../CAPLfunctionsMediaProperties.md) » FrameRate

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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
