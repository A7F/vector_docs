# diagGetParameterSizeCoded

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetParameterSizeCoded(diagRequest obj, char parameterName[])`
- `long diagGetParameterSizeCoded(diagResponse obj, char parameterName[])`

## Method Syntax

- `diagRequest::GetParameterSizeCoded(char* parameterName);`
- `diagResponse::GetParameterSizeCoded(char* parameterName);`

## Description

Returns the length of the coded parameter in bits.

## Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier

## Return Values

If > 0 the number of bits, otherwise an [error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—
