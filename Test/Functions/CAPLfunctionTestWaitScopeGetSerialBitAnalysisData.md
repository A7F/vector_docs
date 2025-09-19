[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitScopeGetSerialBitAnalysisData.md)

**CAPL Functions** » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitScopeGetSerialBitAnalysisData

# testWaitScopeGetSerialBitAnalysisData

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long testWaitScopeGetSerialBitAnalysisData (ScopeAnalyseHandle handle, dword msgField, dword bitNo, ScopeDutyCycleDefinition dutyCycle, ScopeBitDataDutyCycle data);
```

## Description

Returns the serial bit analysis data and duty cycle data for the defined bit.

## Parameters

- **handle**: A unique ID. The same handle must be used for all bit analysis function calls.
  - **ScopeAnalyseHandle Selectors**
    - **Keyword**: handle
    - **Description**: A unique ID
    - **Type**: long

- **msgField**: The field within the message. See `ScopeBitAnalyse.cin`.

- **bitNo**: The bit number within the msg field.

- **dutyCycle**: The duty cycle measurement parameters. See [ScopeDutyCycleDefintion](../../Scope/Classes/CAPLfunctionScopeDutyCycleDefinition.md).

- **data**: The duty cycle data for the defined bit. See [ScopeBitDataDutyCycle](../../Scope/Classes/CAPLfunctionScopeBitDataDutyCycle.md).

## Return Values

- **1**: Success
- **< 0**: Error occurred. See `EScopeCAPLFitDataReturnCode` in `ScopeBitAnalyse.cin`.

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
