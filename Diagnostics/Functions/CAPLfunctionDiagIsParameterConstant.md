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
