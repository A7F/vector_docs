[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitScopeGetSerialBitAnalyseViolationData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitScopeGetSerialBitAnalyseViolationData

# testWaitScopeGetSerialBitAnalyseViolationData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`long testWaitScopeGetSerialBitAnalyseViolationData(ScopeAnalyseHandle handle, long errorNo, ScopeDutyCycleDefinition dutyCycle, ScopeBitDataDutyCycle cycleData, ScopeSerialBitAnalysisViolationData data);`

## Description

Returns the duty cycle data and the violation data of the serial bit analysis for the error number.

## Parameters

- **handle**: A unique ID. The same handle must be used for all bit analysis function calls.

  **ScopeAnalyseHandle Selectors**

  - **Keyword**: handle
  - **Description**: A unique ID
  - **Type**: long

- **errorNo**: The error number the data are requested.

- **dutyCycle**: The duty cycle measurement parameters. See [ScopeDutyCycleDefintion](../../Scope/Classes/CAPLfunctionScopeDutyCycleDefinition.md).

- **cycleData**: The duty cycle data for the defined bit. See [ScopeBitDataDutyCycle](../../Scope/Classes/CAPLfunctionScopeBitDataDutyCycle.md).

- **data**: The serial bit analysis violation data for the error number. See [ScopeSerialBitAnalysisViolationData](../../Scope/Classes/CAPLfunctionScopeSerialBitAnalysisViolationData.md).

## Return Values

- **1**: Success
- **< 0**: Error occurred. See `EScopeCAPLFitDataReturnCode` in `<application>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('"Reusable\\CAPL_Includes\\Scope"'))

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)