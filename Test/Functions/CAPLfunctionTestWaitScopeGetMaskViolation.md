[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitScopeGetMaskViolation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitScopeGetMaskViolation

# testWaitScopeGetMaskViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitScopeGetMaskViolation (ScopeAnalyseHandle handle, long errorIndex, ScopeMaskViolationData maskViolationData); // form 1`
- `long testWaitScopeGetMaskViolation (ScopeAnalyseHandle handle, long errorIndex, frFrame frame, ScopeMaskViolationData2 maskViolationData); // form 2`

## Description

Retrieve the data of the bitmask violations found with [testWaitScopeAnalyseSignal](CAPLfunctionTestWaitScopeAnalyseSignal.md).

## Parameters

- **handle**: A unique ID. The same handle must be used for all bit analysis function calls.

  **ScopeAnalyseHandle Selectors**

  - **Keyword**: handle
  - **Description**: A unique ID
  - **Type**: long

- **errorIndex**: The number of the bitmask error for which the error description shall be returned.

- **maskViolationData**: The error description.

  **ScopeMaskViolationData Selectors**

  - **Keyword**: bitField
  - **Description**: field type, see `ScopeBitAnalyse.cin`
  - **Type**: long

  - **Keyword**: bitNo
  - **Description**: bit number within bit field
  - **Type**: dword

  - **Keyword**: errorType
  - **Description**: reserved
  - **Type**: dword

  - **Keyword**: bitStartTime
  - **Description**: bit start in ns
  - **Type**: int64

  - **Keyword**: thresholdTimeOffset
  - **Description**: distance to bit start in ns
  - **Type**: long

  - **Keyword**: disturbanceTimeStart
  - **Description**: distance of disturbance to bit start in ns
  - **Type**: long

  - **Keyword**: disturbanceTimeEnd
  - **Description**: distance of end of disturbance to bit start in ns
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

  **ScopeMaskViolationData2 Selectors**

  - **Keyword**: bitField
  - **Description**: field type, see `ScopeBitAnalyse.cin`
  - **Type**: long

  - **Keyword**: bitNo
  - **Description**: bit number within bit field
  - **Type**: long

  - **Keyword**: errorType
  - **Description**: reserved
  - **Type**: dword

  - **Keyword**: bitStartTime
  - **Description**: bit start in ns
  - **Type**: dword

  - **Keyword**: disturbanceTimeStart
  - **Description**: distance of disturbance to bit start in ps
  - **Type**: long

  - **Keyword**: disturbanceTimeEnd
  - **Description**: distance of end of disturbance to bit start in ps
  - **Type**: long

  - **Keyword**: Vdist
  - **Description**: measured voltage at the point of the maximum disturbance in mV
  - **Type**: long

  - **Keyword**: Vgiven
  - **Description**: expected voltage at the point of the maximum disturbance in mV
  - **Type**: long

## Return Values

- **1**: Success
- **0**: Timeout
- **< 0**: Error occurred. See `EScopeCAPLFitDataReturnCode` in `ScopeBitAnalyse.cin`

## Example

[Scope Sample Configuration](../../../SampConf/CAN/CANoe/Scope/BitmaskAnalysisCAN.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
