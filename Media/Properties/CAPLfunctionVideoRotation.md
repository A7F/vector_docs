[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionVideoRotation.md)

**CAPL Functions** » **Media API** » **Properties** » **VideoRotation**

# VideoRotation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

VideoRotation

## Description

Specifies the rotation of a video frame in the counter-clockwise direction.

## Data Type

dword

## Remarks

Video from a handheld device, such as a mobile phone, is often rotated by 90, 180, or 270 degrees. If the camera stores the orientation as metadata in the video file, the image can be adjusted at the time of playback.

If this property set to VideoRotationFormat_90, it means that the content has been rotated 90 degrees in the counter-clockwise direction. If the content was rotated 90 degrees in the clockwise direction, the attribute value would be VideoRotationFormat_270.

Supported values for this property:

- VideoRotationFormat_0 = 0
- VideoRotationFormat_90 = 90
- VideoRotationFormat_180 = 180
- VideoRotationFormat_270 = 270

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)