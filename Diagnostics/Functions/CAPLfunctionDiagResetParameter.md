# diagResetParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagResetParameter (diagResponse obj, char parameterName[])`
- `long diagResetParameter (diagRequest obj, char parameterName[])`

## Method Syntax

- `diagResponse::ResetParameter (char parameterName[])`
- `diagRequest::ResetParameter (char parameterName[])`

## Description

Sets the parameter to its default value.

## Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—
