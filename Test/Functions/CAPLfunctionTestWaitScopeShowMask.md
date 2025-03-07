[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitScopeShowMask.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitScopeShowMask

# testWaitScopeShowMask

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitScopeShowMask (ScopeAnalyseHandle handle, dword msgFieldStart, long startBitNo, long bitCount);` // form 1
- `long testWaitScopeShowMask (ScopeAnalyseHandle handle, frFrame frame, dword msgFieldStart, long startBitNo, long bitCount);` // form 2

## Description

The defined frame cutout of the previously analyzed frame together with the bitmask is shown in the scope's [Diagram](../../../CANoeCANalyzer/SCOPE/ScopeDiagram.md) view. The enlarged area is automatically scaled in time direction. Only the differential signal will be displayed.

- Form 1: Can only be used for CAN bitmask analysis.
- Form 2: Can only be used for FlexRay bitmask analysis.

## Parameters

- **handle**: A unique ID. The same handle must be used for all bit analysis function calls.
  - **struct ScopeAnalyseHandle Selectors**:
    - **Keyword**: handle
    - **Description**: A unique ID
    - **Type**: long

- **frFrame**: The FlexRay frame to be displayed.

- **msgFieldStart, startBitNo**: The start of the cutout to be displayed.
  - **msgFieldStart**: see `<application>\Reusable\CAPL_Includes\Scope\ScopeBitAnalyse.cin`
  - **startBitNo**: A bit index in the message field

## Return Values

- **1**: Success
- **0**: Timeout
- **< 0**: Error occurred. See **EScopeCAPLFitDataReturnCode** in `<application>\Reusable\CAPL_Includes\Scope\ScopeBitAnalyse.cin`

## Example

[Scope Sample Configuration](../../../SampConf/CAN/CANoe/Scope/BitmaskAnalysisCAN.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)