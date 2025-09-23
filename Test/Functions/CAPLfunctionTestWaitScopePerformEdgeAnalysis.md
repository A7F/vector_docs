# testWaitScopePerformEdgeAnalysis

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitScopePerformEdgeAnalysis(message frame, ScopeAnalyseRange analyseRange, dword flags, long thresholdStart long thresholdEnd, ScopeEdgeAnalyseResult parameter[], dword parameterCount, ScopeAnalyseHandle handle) //Form 1`
- `long testWaitScopePerformEdgeAnalysis(linFrame frame, ScopeAnalyseRange analyseRange, dword flags, long thresholdStart long thresholdEnd, ScopeEdgeAnalyseResult parameter[], dword parameterCount, ScopeAnalyseHandle handle) //Form 2`
- `long testWaitScopePerformEdgeAnalysis(frFrame frame, ScopeAnalyseRange analyseRange, dword flags, long thresholdStart long thresholdEnd, ScopeEdgeAnalyseResult parameter[], dword parameterCount, ScopeAnalyseHandle handle) //Form 3`
- `long testWaitScopePerformEdgeAnalysis(char nodeName[], ScopeAnalyseRange analyseRange, dword flags, long thresholdStart long thresholdEnd, ScopeEdgeAnalyseResult parameter[], dword parameterCount, ScopeAnalyseHandle handle) //Form 4`

### Description

Perform an edge analysis for falling/rising edges of a specific frame or a complete node.

### Parameters

- **frame //Form 1,2,3**: The CAN, LIN or FlexRay frame should be analyzed.
- **nodeName //Form 4**: The node should be analyzed.
- **analyseRange**: The start and end of the transition time measurement. See Class: [scopeAnalyseRange](../../Scope/Classes/CAPLfunctionScopeAnalyseRange.md).
- **flags**:
  - **Bits**:
    - 0: Define threshold level unit:
      - 0 = Threshold level in mV
      - 1 = Threshold level in %
    - 1-3: Select signal for transition time measurement (only valid for CAN)
      - Bit 1 = 1 Use CANhigh
      - Bit 2 = 1 Use CANLow
      - Bit 3 = 1 Use CANdiff
    - 4-5: Rising/falling edge selection
      - Bit 4 = 1 Use rising edges
      - Bit 5 = 1 Use falling edges
    - 6:
      - 0 = Use last occurrence for transition time measurement, where the voltage level is above or below the threshold level.
      - 1 = Use first occurrence for transition time measurement, where the voltage level is above or below the threshold level.
  - All other bits are reserved and must be set to 0.
- **thresholdStart, thresholdEnd**: The start/end threshold should be used. Can be defined as % or mV value. These values are used to measure the transition time of an edge.
- **parameters**: The parameters should be measured. (See [ScopeEdgeAnalyseResult](../../Scope/Classes/CAPLfunctionScopeEdgeAnalysisResult.md))
- **parameterCount**: The parameter count which are contained within the parameters array.
- **handle**: A unique ID.

### ScopeAnalyseHandle Selectors

- **Keyword**: handle
- **Description**: A unique ID
- **Type**: long

### Return Values

- **1**: Successful
- **\< 0**: Error occurred. See EScopeCAPLFitDataReturnCode in ScopeBitAnalyse.cin

### Example

—

[ScopeEdgeAnalysisResult](../../Scope/Classes/CAPLfunctionScopeEdgeAnalysisResult.md) • [ScopeAnalyseRange](../../Scope/Classes/CAPLfunctionScopeAnalyseRange.md)
