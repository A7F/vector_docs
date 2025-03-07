[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitScopeGetFieldLengthData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitScopeGetFieldLengthData

# testWaitScopeGetFieldLengthData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long testWaitScopeGetFieldLengthData (ScopeAnalyseHandle handle,  dword bitNo, ScopeFieldLengthData bitData);
```

## Description

Returns the number of bits contained within the defined range and the length of this range.

## Parameters

- **handle**  
  A unique ID. The same handle must be used for all bit analysis function calls.

  **ScopeAnalyseHandle Selectors**

  - **Keyword**: handle
  - **Description**: A unique ID
  - **Type**: long

- **bitNo**  
  The number of the bit from which the information is requested.

  **Note**: The bit number is 0-based and cannot be greater than the return value of the function [testWaitForScopePerformFieldLengthMeasurement](CAPLfunctionTestWaitForScopePerformFieldLengthMeasurement.md).

- **bitData**  
  Returns the information for the bit (see [ScopeFieldLengthData](../../Scope/Classes/CAPLfunctionScopeFieldLengthData.md)).

## Return Values

- **1**  
  Successful

- **0**  
  Timeout

- **< 0**  
  Error occurred. See **EScopeCAPLFitDataReturnCode** in `<application>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('&quot;Reusable\\CAPL_Includes\\Scope&quot;'))

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)