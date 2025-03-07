[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagIsParameterConstant.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagIsParameterConstant, diagIsRespParameterConstant

# diagIsParameterConstant, diagIsRespParameterConstant

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagIsParameterConstant(diagResponse object, char[] qualifier)`
- `long diagIsParameterConstant(diagRequest object, char[] qualifier)`
- `long diagIsRespParameterConstant(diagRequest object, char[] qualifier)`

## Method Syntax

- `diagResponse::IsParameterConstant(char[] qualifier)`
- `diagRequest::IsParameterConstant(char[] qualifier)`
- `diagRequest::IsRespParameterConstant(char[] qualifier)`

## Description

Returns 1 if the parameter is declared constant in the diagnostic description.

## Parameters

- **object**: Diagnostics object
- **qualifier**: Parameter qualifier

## Return Values

1 for true or [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)