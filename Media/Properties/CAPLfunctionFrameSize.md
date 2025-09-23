# FrameSize

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Property

FrameSize

## Description

Width and height of a video frame, in pixels.

## Data Type

qword

## Remarks

- The upper 32 bits contain the width and the lower 32 bits contain the height.
- To set this attribute, use the [MediaSetPropertySize](../Functions/CAPLfunctionMediaSetPropertySize.md) function.
- To get this attribute, use the [MediaGetPropertySize](../Functions/CAPLfunctionMediaGetPropertySize.md) function.
