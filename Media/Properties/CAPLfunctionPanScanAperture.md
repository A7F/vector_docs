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
