[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetParameterSizeRaw.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetParameterSizeRaw

# diagGetParameterSizeRaw

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetParameterSizeRaw(diagRequest obj, char parameterName[])`
- `long diagGetParameterSizeRaw(diagResponse obj, char parameterName[])`

## Method Syntax

- `diagRequest::GetParameterSizeRaw(char* parameterName);`
- `diagResponse::GetParameterSizeRaw(char* parameterName);`

## Description

Returns the length of the raw parameter in bits (raw stream) including leading size byte, terminating zeros etc.

## Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier

## Return Values

If > 0 the number bits, otherwise an [error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)