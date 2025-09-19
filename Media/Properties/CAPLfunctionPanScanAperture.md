[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionPanScanAperture.md)

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » [Properties](../CAPLfunctionsMediaProperties.md) » PanScanAperture

# PanScanAperture

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

PanScanAperture

## Description

Defines the pan/scan aperture, which is the 4×3 region of video that should be displayed in pan/scan mode.

## Data Type

dword

## Remarks

- This property is used to crop wide-screen video to a 4:3 aspect ratio. The pan/scan aperture is used only in pan/scan mode, which is enabled by setting the [PanScanEnabled](CAPLfunctionPanScanEnabled.md) property to **TRUE**.
- If pan/scan mode is not enabled, use the display aperture, specified by the [MinimumDisplayAperture](CAPLfunctionMinimumDisplayAperture.md) property.
- If this property is not set, the pan/scan aperture is assumed to be the entire video frame.

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
