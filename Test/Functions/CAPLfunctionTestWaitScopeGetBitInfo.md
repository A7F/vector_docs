[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitScopeGetBitInfo.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitScopeGetBitInfo

# testWaitScopeGetBitInfo

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`long testWaitScopeGetBitInfo(ScopeAnalyseHandle handle, dword msgFieldStart, long startBitNo, dword msgFieldEnd, long EndBitNo, ScopeMaskViolationData data);`

## Description

After a signal was analyzed with the function [testWaitScopeAnalyseSignal](CAPLfunctionTestWaitScopeAnalyseSignal.md), the average values of the voltages of CAN_H, CAN_L, and CAN_Diff are calculated for a defined bit range.

## Parameters

- **handle**: A unique ID. The same handle must be used for all bit analysis function calls.
  - **struct ScopeAnalyseHandle Selectors**
    - **Keyword**: handle
    - **Description**: A unique ID
    - **Type**: long

- **msgFieldStart, startBitNo, msgFieldEnd, EndBitNo**: The cutout of the frame to be analyzed.
  - **msgFieldStart, msgFieldEnd**: See `<application>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('"Reusable\\CAPL_Includes\\Scope"'))
  - **startBitNo, endBitNo**: A bit index in the message field

- **maskViolationData**: The error description.
  - **ScopeMaskViolationData Selectors**
    - **Keyword**: bitField
    - **Description**: field type, see `<application>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('"Reusable\\CAPL_Includes\\Scope"'))
    - **Type**: long
    - **Keyword**: bitNo
    - **Description**: bit number within bit field
    - **Type**: dword
    - **Keyword**: errorType
    - **Description**: reserved
    - **Type**: dword
    - **Keyword**: bitStartTime
    - **Description**: bit start in ns
    - **Type**: long
    - **Keyword**: samplePointVoltage
    - **Description**: voltage at sampling point in mV
    - **Type**: long
    - **Keyword**: domVoltageCANH
    - **Description**: voltage at sampling point for dominant bit for signal CAN High
    - **Type**: long
    - **Keyword**: recVoltageCANH
    - **Description**: voltage at sampling point for recessive bit for signal CAN High
    - **Type**: long
    - **Keyword**: domVoltageCANL
    - **Description**: voltage at sampling point for dominant bit for signal CAN Low
    - **Type**: long
    - **Keyword**: recVoltageCANL
    - **Description**: voltage at sampling point for recessive bit for signal CAN Low
    - **Type**: long
    - **Keyword**: domVoltageDiff
    - **Description**: voltage at sampling point for dominant bit for signal CAN Diff
    - **Type**: long
    - **Keyword**: recVoltageDiff
    - **Description**: voltage at sampling point for recessive bit for signal CAN Diff
    - **Type**: long
    - **Keyword**: V2_V3
    - **Description**: reserved
    - **Type**: long
    - **Keyword**: thresholdVoltage
    - **Description**: threshold level in mV relative to scope ground
    - **Type**: long

## Return Values

- **1**: Success
- **0**: Timeout
- **< 0**: Error occurred. See **EScopeCAPLFitDataReturnCode** in `<application>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('"Reusable\\CAPL_Includes\\Scope"'))

## Example

[Scope Sample Configuration](../../../SampConf/CAN/CANoe/Scope/BitmaskAnalysisCAN.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
