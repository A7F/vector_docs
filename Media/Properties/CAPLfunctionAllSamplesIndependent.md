# AllSamplesIndependent

**Valid for**: CANoe DE • CANoe4SW DE

## Property

AllSamplesIndependent

## Description

Specifies for a media type whether each sample is independent of the other samples in the stream.

## Data Type

dword (treat as a Boolean value)

## Remarks

If this property is **FALSE**, some samples cannot be used without referring to other samples in the stream. For example, if a video format contains delta frames, this property should be **FALSE**. Set this property to **TRUE** for all uncompressed media types.

**See Also**

- [AllSamplesIndependent](javascript:void(0);)
- [Compressed](CAPLfunctionCompressed.md#aanchor22508)
- [FixedSizeSamples](CAPLfunctionFixedSizeSamples.md#aanchor27431)
- [MajorType](CAPLfunctionMajorType.md#aanchor6864)
- [SampleSize](CAPLfunctionSampleSize.md#aanchor13699)
- [Subtype](CAPLfunctionSubType.md#aanchor20044)
