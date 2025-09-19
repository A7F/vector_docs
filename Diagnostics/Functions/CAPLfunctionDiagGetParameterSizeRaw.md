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
