[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitScopePerformSignalTransitionTime.md)

**CAPL Functions** » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitScopePerformSignalTransitionTime

# testWaitScopePerformSignalTransitionTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitScopePerformSignalTransitionTime (message aMessage, ScopeAnalyseRange range, dword flags, long thresholdStart, long thresholdEnd, ScopeBitTransitionTimeResult result, ScopeAnalyseHandle handle); // form 1`
- `long testWaitScopePerformSignalTransitionTime (char nodeName[], ScopeAnalyseRange range, dword flags, long thresholdStart, long thresholdEnd, ScopeBitTransitionTimeResult result, ScopeAnalyseHandle handle); // form 2`
- `long testWaitScopePerformSignalTransitionTime (linFrame aMessage, ScopeAnalyseRange range, dword flags, long thresholdStart, long thresholdEnd, ScopeBitTransitionTimeResult result, ScopeAnalyseHandle handle); // form 3`
- `long testWaitScopePerformSignalTransitionTime (frFrame aMessage, ScopeAnalyseRange range, dword flags, long thresholdStart, long thresholdEnd, ScopeBitTransitionTimeResult result, ScopeAnalyseHandle handle); // form 4`

## Description

- **Form 1**: Measures the transition time of rising and falling edges of a CAN message within the defined area.
- **Form 2**: Measures the transition time of rising and falling edges of all Tx messages of an ECU node within the defined area.
- **Form 3**: Measures the transition time of rising and falling edges of a LIN message within the defined area.
- **Form 4**: Measures the transition time of rising and falling edges of a FlexRay message within the defined area.

## Parameters

- **aMessage**: The message to be analyzed.
- **nodeName**: The ECU node name of a database node.
- **range**: The start and end of the transition time measurement. See [Class: scopeAnalyseRange](../../Scope/Classes/CAPLfunctionScopeAnalyseRange.md).
- **flags**:
  - **Bits**:
    - 0: Define threshold level unit:
      - 0 = Threshold level in mV
      - 1 = Threshold level in %
    - 1-3: Select signal for transition time measurement (only valid for CAN):
      - Bit 1 = 1 Use CANhigh
      - Bit 2 = 1 Use CANLow
      - Bit 3 = 1 Use CANdiff
    - 4-5: Rising/falling edge selection:
      - Bit 4 = 1 Use rising edges
      - Bit 5 = 1 Use falling edges
    - 6:
      - 0 = Use last occurrence for transition time measurement, where the voltage level is above or below the threshold level.
      - 1 = Use first occurrence for transition time measurement, where the voltage level is above or below the threshold level.
    - All other bits are reserved and must be set to 0.
- **result**: The transition time measurement result.
  - **ScopeBitTransitionTimeResult Selectors**:
    - **minValue**: The minimal transition time (float)
    - **maxValue**: The maximal transition time (float)
    - **averageValue**: The average transition time overall measured edges (float)
    - **stdDeviation**: The standard deviation of the transition time measurement (float)
    - **scopeSamplingPeriod**: The configured sample period of the scope device (float)
    - **countAnalyzedEdges**: The count of analyzed edges (long)
    - **countAnalyzedFrames**: The count of analyzed frames (long)
- **handle**: A unique ID. The same handle must be used for all bit analysis function calls.
  - **ScopeAnalyseHandle Selectors**:
    - **handle**: A unique ID (long)

## Return Values

- **1**: success
- **0**: timeout
- **< 0**: Error occurred. See `EScopeCAPLFitDataReturnCode` in `ScopeBitAnalyse.cin`

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
