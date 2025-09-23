# Compressed

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Property

Compressed

## Description

Specifies for a media type whether the media data is compressed.

## Data Type

dword (treat as a Boolean value)

## Remarks

- If this property is **TRUE**, the media type is a compressed format. Otherwise, either the media type is uncompressed or the compression type is not known.
- This property is not guaranteed to be set to **TRUE** for all compressed formats, so applications should generally not rely on this property. The most reliable way to determine whether a format is compressed is to maintain a list of known formats. If an application does not recognize a format, as specified in the [Subtype](CAPLfunctionSubType.md) property, it should not assume anything about the compression of the format.
- To determine whether a format uses temporal compression (meaning that some samples are computed as deltas from earlier samples), check the [AllSamplesIndependent](CAPLfunctionAllSamplesIndependent.md) property.
