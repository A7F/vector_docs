[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLFunctionTestWaitScopePerformEyeDiagramAnalysis.md)

## CAPL Functions » Scope » testWaitScopePerformEyeDiagramAnalysis

# testWaitScopePerformEyeDiagramAnalysis

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitScopePerformEyeDiagramAnalysis(message frame, dword flags, dword groupNumber, ScopeSinglePolygonBitMask bitMask, ScopeAnalyseHandle handle); // form 1`
- `long testWaitScopePerformEyeDiagramAnalysis(linFrame frame, dword flags, dword groupNumber, ScopeSinglePolygonBitMask bitMask, ScopeAnalyseHandle handle); // form 2`
- `long testWaitScopePerformEyeDiagramAnalysis(frFrame frame, dword flags, dword groupNumber, ScopeSinglePolygonBitMask bitMask, ScopeAnalyseHandle handle); // form 3`
- `long testWaitScopePerformEyeDiagramAnalysis(char nodeName[], dword flags, dword groupNumber, ScopeSinglePolygonBitMask bitMask, ScopeAnalyseHandle handle); // form 4`

### Description

Perform a bit analysis for the eye diagram.

### Parameters

- **frame**: The CAN, LIN or FlexRay frame should be analysed.
- **nodeName**: The node should be analysed.
- **flags**:
  - Form 1 (CAN): Reserved must be set to 0.
  - Form 2 (LIN): Reserved must be set to 0.
  - Form 3(FlexRay) and Form 4(FlexRay Node):
    - 0-2:
      - 0 = Analyze only frames in Key Slots
      - 1 = Analyze only frames of static segment
      - 2 = Analyze only frames in dynamic segment
      - 3 = Use all frame for analysis
    - 3:
      - 0 = Do not contain BSS
      - 1 = Contain BSS
  - Form 4(CAN and LIN): Reserved must be set to 0.
- **groupNumber**:
  - Form 1 (CAN):
    - 0: Standard Range for a CAN Frame
    - 1: Arbitration Range for a CAN Frame
    - 2: Acknowledge Field CAN Frame
    - 3: Entire CAN Frame
    - 4: Standard Range for a CAN FD Frame
    - 5: Arbitration Range for a CAN FD Frame
    - 6: Acknowledge Field CAN FD Frame
  - Form 2 (LIN):
    - 0: Standard Range for LIN frame (Header and Response)
    - 1: Only Header for LIN frame
    - 2: Only Response for LIN Frame
  - Form 3 (FlexRay):
    - 0: Entire FlexRay frame
    - 1: FSS Field
    - 2: Header Segment
    - 3: ProtocolFlags
    - 4: Frame ID
    - 5: Payload Length
    - 6: Header CRC
    - 7: Cycle Count
    - 8: Payload Segment
    - 9: Frame CRC
  - Form 4(Node): Depends on the bus system of the node. (See Form 1 to Form 3)
- **bitMask**: The bitmask should be used for the analysis. (See [ScopeSinglePolygonBitMask](../../Scope/Classes/CAPLFunctionScopeSinglePolygonBitMask.md))
- **handle**: A unique ID. The same handle must be used to request the violation data with the function [testWaitScopeGetEyeDiagramAnalysis](CAPLfunctionTestWaitScopeGetEyeDiagramAnalysis.md).

### Return Values

- **1**: Successful
- **< 0**: Error occurred. See `EScopeCAPLFitDataReturnCode` in `<application>\Reusable\CAPL_Includes\Scope\ScopeBitAnalyse.cin`

### Example

—
