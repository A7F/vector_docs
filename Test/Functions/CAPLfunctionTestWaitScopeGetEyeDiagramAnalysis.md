[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitScopeGetEyeDiagramAnalysis.md)

# testWaitScopeGetEyeDiagramAnalysis

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitScopeGetEyeDiagramAnalysis

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitScopeGetEyeDiagramAnalysis(ScopeAnalyseHandle handle, dword violationNumber, message frame, ScopeSerialBitAnalysisViolationData data); // form 1`
- `long testWaitScopeGetEyeDiagramAnalysis(ScopeAnalyseHandle handle, dword violationNumber, linFrame frame, ScopeSerialBitAnalysisViolationData data); // form 2`
- `long testWaitScopeGetEyeDiagramAnalysis(ScopeAnalyseHandle handle, dword violationNumber, frFrame frame, ScopeSerialBitAnalysisViolationData data); // form 3`

## Description

Returns the violation data of the eye diagram analysis for the error number.

## Parameters

- **handle**: A unique ID. The same handle must be used as for the eye diagram analysis call with the function [testWaitScopePerformEyeDiagramAnalysis](CAPLFunctionTestWaitScopePerformEyeDiagramAnalysis.md).

- **ScopeAnalyseHandle Selectors**:
  - **Keyword**: `handle`
  - **Description**: A unique ID
  - **Type**: `long`

- **frame**: Returns the relevant data for the frame where the error occurred.

- **violationNumber**: The violation number the data are requested.

- **data**: The serial bit analysis violation data for the error number. See [ScopeSerialBitAnalysisViolationData](../../Scope/Classes/CAPLfunctionScopeSerialBitAnalysisViolationData.md).

## Return Values

- **1**: Successful
- **< 0**: Error occurred. See **EScopeCAPLFitDataReturnCode** in `<application>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('"Reusable\\CAPL_Includes\\Scope"'))

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)