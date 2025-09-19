[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForScopePerformFieldLengthMeasurement.md)

**CAPL Functions** » **Scope** » **testWaitForScopePerformFieldLengthMeasurement**

# testWaitForScopePerformFieldLengthMeasurement

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long testWaitForScopePerformFieldLengthMeasurement (frFrame msg, dword msgFieldStart, dword msgFieldEnd, dword bitStartNo, dword bitEndNo, qword fieldLength, ScopeAnalyseHandle handle);
```

## Description

Returns the number of bits contained within the defined range and the length of this range.

## Parameters

- **msg**: The message where the field length should be measured.
- **msgFieldStart**: Defines the start of the measurement range.
- **msgFieldEnd**: Defines the end of the measurement range.
- **bitStartNo**: The bit within the start field where the measurement starts.
- **bitEndNo**: The bit within the end field where the measurement ends.
- **fieldLength**: Returns the length of the defined range.
- **handle**: A unique ID. The same handle must be used for all bit analysis function calls.

### ScopeAnalyseHandle Selectors

- **Keyword**: handle
- **Description**: A unique ID
- **Type**: long

## Return Values

- **> 0**: Number of bits
- **0**: Timeout
- **< 0**: Error occurred. See `EScopeCAPLFitDataReturnCode` in `<application>\Reusable\CAPL_Includes\Scope\ScopeBitAnalyse.cin`

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
