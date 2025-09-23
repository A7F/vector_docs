[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitScopeGetAnalysedBitSegments.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitScopeGetAnalysedBitSegments

# testWaitScopeGetAnalysedBitSegments

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long testWaitScopeGetAnalysedBitSegments(long bitNumber, ScopeAnalyseBitSegmentData segmentData, dword noOfSegments);
```

## Description

Request the analysis data for a single bit. The analysis data are calculated by calling the function [testWaitForScopeAnalyseBitSegments](CAPLfunctionTestWaitForScopeAnalyseBitSegments.md).

## Parameters

- **bitNumber**: The bit number the data are requested. The number must be between 0 and the return value of the function [testWaitForScopeAnalyseBitSegments](CAPLfunctionTestWaitForScopeAnalyseBitSegments.md).
- **segmentData**: Array that holds the analysis data for the segments of one bit.

  **ScopeAnalyseBitSegmentData selectors:**
  - **SegmentStart**: Start of segment within bit in %
  - **SegmentEnd**: End of segment within bit in %
  - **BitField**: Scope enum for bit type or field type.
  - **BitNo**: Number of bit within bit field
  - **BitLevel**: 0 – dominant bit level 1 – recessive bit level
  - **ReferenceVoltage**: Voltage of reference point in mV
  - **MinVoltage**: Minimal voltage within the segment in mV
  - **MaxVoltage**: Maximal voltage within the segment in mV
  - **AvgVoltage**: Average voltage within the segment in mV

- **noOfSegments**: Number of the bit segments. The Number should be the same used by the function [testWaitForScopeAnalyseBitSegments](CAPLfunctionTestWaitForScopeAnalyseBitSegments.md) (maximum = 10).

## Return Values

- **0**: Timeout
- **< 0**: Error occurred. See EScopeCAPLFitDataReturnCode in [ScopeBitAnalyse.cin](javascript:startDemoLoader('"Reusable\\CAPL_Includes\\Scope"'))
- **> 0**: Number of written segments.

## Example

—
