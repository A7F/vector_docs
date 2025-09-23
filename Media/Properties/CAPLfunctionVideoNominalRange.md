# VideoNominalRange

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Property

VideoNominalRange

## Description

Specifies the nominal range of the color information in a video media type.

## Data Type

dword

## Remarks

The value of this property is one of the following:

- NominalRange_Unknown = 0,
- NominalRange_Normal = 1,
- NominalRange_Wide = 2,
- NominalRange_0_255 = 1,
- NominalRange_16_235 = 2,
- NominalRange_48_208 = 3,
- NominalRange_64_127 = 4

**H.264/AVC encoders:**

On the output media type, **VideoNominalRange** can be set with NominalRange_0_255 and NominalRange_16_235.

H.264/AVC encoder shall treat NominalRange_Unknown as NominalRange_16_235.

H.264/AVC encoder shall reject an output media type when **VideoNominalRange** is set to NominalRange_48_208, NominalRange_64_127, or any other values not defined on NominalRange.
