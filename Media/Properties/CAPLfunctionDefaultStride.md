# DefaultStride

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

DefaultStride

## Description

Default surface stride, for an uncompressed video media type. Stride is the number of bytes needed to go from one row of pixels to the next.

## Data Type

dword (treat as a long value)

## Remarks

- The property value is stored as a dword, but should be cast to a 32 bit signed integer value. Stride can be negative.
- Stride is positive for top-down images, and negative for bottom-up images.
- This property gives the stride for a contiguous representation of the image in memory; that is, a representation with no additional padding bytes after each row.
