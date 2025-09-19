[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionPixelAspectRatio.md)

**CAPL Functions** » **Media API** » **Properties** » PixelAspectRatio

# PixelAspectRatio

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

PixelAspectRatio

## Description

Pixel aspect ratio for a video media type.

## Data Type

qword

## Remarks

- The upper 32 bits contain the numerator of the pixel aspect ratio and the lower 32 bits contain the denominator. The numerator is the horizontal component of the aspect ratio; the denominator is the vertical component.
- To set this property, use the [MediaSetPropertyRatio](../Functions/CAPLfunctionMediaSetPropertyRatio.md) function.
- To get this property, use the [MediaGetPropertyRatio](../Functions/CAPLfunctionMediaGetPropertyRatio.md) function.
- The pixel aspect ratio describes the shape of the pixels in the displayed video image. Set this property if the image has non-square pixels. To display correctly on a display device with square pixels, the image must be scaled by the inverse of the image's pixel aspect ratio.

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
