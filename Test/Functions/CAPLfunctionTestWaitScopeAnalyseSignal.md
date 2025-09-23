# testWaitScopeAnalyseSignal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitScopeAnalyseSignal (message aMessage, dword flags, dword msgFieldStart, dword msgFieldEnd, ScopeBitMaskPolygon bitMaskPolygon, long domVoltageThreshold , long recVoltageThreshold, ScopeAnalyseHandle handle); // form 1`
- `long testWaitScopeAnalyseSignal (char nodeName[], dword flags, ScopeBitMaskPolygon bitMaskPolygon, ScopeAnalyseResult analyzeResult, ScopeAnalyseHandle handle); // form 2`

## Description

- **Form 1**: Checks the bits of a CAN message against the defined bitmask.
- **Form 2**: Checks the bits of FlexRay frames which are transmitted by one node against the defined bitmask.

## Parameters

- **aMessage**: The CAN message to be analyzed.
- **flags**:
  - **Form 1 (CAN)**:
    - Bit 0 = 0: synchronize on recessive to dominant edges
    - Bit 0 = 1: synchronize on all edges
  - **Form 2 (FlexRay)**:
    - Bits 0-2:
      - 0 = Analyze only frames in Key Slots
      - 1 = Analyze only frames of static segment
      - 2 = Analyze only frames in dynamic segment
      - 3 = Use all frame for analysis
- **msgFieldStart, msgFieldEnd**: The start and end of the cutout to be fitted.
- **bitMaskPolygon**: The bitmask which shall be used.
  - **ScopeBitMaskPolygon Selectors**:
    - **maskPointCount**: Count of the points in the mask-arrays (Type: long)
    - **data_0_Mask**: CAN: Voltage level in mV for dominant bits FlexRay: Voltage level in mV for Data0 (Type: long[])
    - **data_1_Mask**: CAN: Voltage level in mV for recessive bits FlexRay: Voltage level in mV for Data1 (Type: long[])
    - **timeOffset**: Relative position within bit in percent (Type: double[])
- **domVoltageThreshold, recVoltageThreshold**: The voltage levels in millivolt used from the bit parser for detecting dominant and recessive bits.
- **handle**: A unique ID. The same handle must be used for all bit analysis function calls.
  - **ScopeAnalyseHandle Selectors**:
    - **handle**: A unique ID (Type: long)
- **nodeName**: The name of the node.
- **analyzeResult**: Results of the analysis.
  - **ScopeAnalyseResult Selectors**:
    - **result**: The result of the analysis. (1 = pass, 0 = failed) (Type: byte)
    - **analysedFrameCount**: Count of the analyzed frames (Type: long)
    - **framesWithDecodeFailure**: Count of frames with decoding errors (Type: long)
    - **framesWithMaskViolations**: Count of frames with bitmask violations (Type: long)
    - **bitFailureCount**: Count of bits with mask violations (Type: long)

## Return Values

- **Form 1**:
  - **0**: Success
  - **\< 0**: Error occurred. See EScopeCAPLFitDataReturnCode in ScopeBitAnalyse.cin
  - **\> 0**: Number of errors found.
- **Form 2**:
  - **1**: Success
  - **0**: Timeout
  - **\< 0**: Error occurred. See EScopeCAPLFitDataReturnCode in ScopeBitAnalyse.cin

## Example

[Scope Sample Configuration](../../../SampConf/CAN/CANoe/Scope/BitmaskAnalysisCAN.md)
