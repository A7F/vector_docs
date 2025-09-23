# PanScanEnabled

**Valid for**: CANoe DE • CANoe4SW DE

## Property

PanScanEnabled

## Description

Specifies whether pan/scan mode is enabled.

## Data Type

dword (treat as a Boolean value)

## Remarks

- If this property is **TRUE**, only the pan/scan region of the video should be displayed. The pan/scan region is specified by the [PanScanAperture](CAPLfunctionPanScanAperture.md) property.
- If this property is **FALSE** or not set, the entire display aperture of the video should be displayed. The display aperture is specified by the [MinimumDisplayAperture](CAPLfunctionMinimumDisplayAperture.md) property.
- If you set this property to **TRUE**, also set the value of the [PanScanAperture](CAPLfunctionPanScanAperture.md) property.
