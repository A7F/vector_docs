# diag_SetDataSegmentation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with the implementation of the generic CAPL callback interface!

## Function Syntax

```plaintext
long diag_SetDataSegmentation 
(long mode, DWORD maxSegmentSize, DWORD segmentSeparationTime);
```

## Description

Configures the segmentation of diagnostic data at the transmission.

## Parameters

- **mode**  
  Segmentation mode defines whether the transferred data must be segmented (used with VW TP 2.0).
  - **Values**:
    - 0: default value, no segmentation; other function parameters are ignored; no segment header is used (ISO TP)
    - 1: Segment header (2 byte length value) is used; segmentation is activated, if the maxSegmentSize > 0 (VW TP 2.0)

- **maxSegmentSize**  
  Maximum length of a segment, header inclusive.  
  The value 0 implies that the segment may have any length.

- **segmentSeparationTime**  
  Distance between sending of the segments in milliseconds.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—
