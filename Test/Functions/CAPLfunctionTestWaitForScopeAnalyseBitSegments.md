# testWaitForScopeAnalyseBitSegments

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
long testWaitForScopeAnalyseBitSegments(message aMessage, ScopeAnalyseBitSegment bitSegments[], dword noOfSegments, dword referenceVoltagePoint, dword flags, dword msgFieldStart, dword msgFieldEnd);
```

## Description

Starts an analysis for the defined bit segments for each bit, which is within the defined range. The result of the analysis can be requested with the function [testWaitScopeGetAnalysedBitSegments](CAPLfunctionTestWaitScopeGetAnalysedBitSegments.md).

## Parameters

- **aMessage**: The message where the bits should be analyzed.
- **bitSegment**: Array that defines the bit segments of a bit for the analysis (maximum number = 10).

  **ScopeAnalyseBitSegment Selectors**:

  - **SegmentStart**: Start of the bit segment in percent of the bit length (100% = nominal bit length)
  - **SegmentEnd**: End of the bit segment in percent of the bit length (100% = nominal bit length)

- **noOfSegments**: Number of the bit segments used for the analysis.
- **referenceVoltagePoint**: The reference voltage point within the bit in %.
- **flags**:

  - **0**: CAN high signal used for analysis
  - **1**: CAN low signal used for analysis
  - **2**: CAN diff signal used for analysis
  - **3**: CAN common mode voltage (CMV) used for analysis

  All other bits are reserved and must be set to 0.

- **msgFieldStart, msgFieldEnd**: Start and end field of the bit range.

## Return Values

- **0**: Timeout
- **\< 0**: Error occurred. See EScopeCAPLFitDataReturnCode in `ScopeBitAnalyse.cin`
- **\> 0**: Number of analyzed bits.

## Example

—
