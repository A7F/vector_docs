# diagSetComplexParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagSetComplexParameter (diagResponse obj, char parameterName[], DWORD iteration, char subParameter[], double numValue)`
- `long diagSetComplexParameter (diagRequest obj, char parameterName[], DWORD iteration, char subParameter[], double numValue)`
- `long diagSetComplexParameter (diagResponse obj, char parameterName[], DWORD iteration, char subParameter[], char symbValue[])`
- `long diagSetComplexParameter (diagRequest obj, char parameterName[], DWORD iteration, char subParameter[], char symbValue[])`
- `long diagSetComplexParameter (diagResponse obj, long mode, char parameterName[], DWORD iteration, char subParameter[], char valueIn[])`
- `long diagSetComplexParameter (diagRequest obj, long mode, char parameterName[], DWORD iteration, char subParameter[], char valueIn[])`

## Method Syntax

- `diagResponse::SetComplexParameter (char parameterName[], DWORD iteration, char subParameter[], double numValue)`
- `diagRequest::SetComplexParameter (char parameterName[], DWORD iteration, char subParameter[], double numValue)`
- `diagResponse::SetComplexParameter (char parameterName[], DWORD iteration, char subParameter[], char symbValue[])`
- `diagRequest::SetComplexParameter (char parameterName[], DWORD iteration, char subParameter[], char symbValue[])`
- `diagResponse::SetComplexParameter (long mode, char parameterName[], DWORD iteration, char subParameter[], char valueIn[])`
- `diagRequest::SetComplexParameter (long mode, char parameterName[], DWORD iteration, char subParameter[], char valueIn[])`

## Description

Sets one of the sub-parameters within a complex parameter to the specified (numeric or symbolic) value.

For this first the complex parameter, that is, the name of the iteration, must be specified; then the number of repetitions of the sub-parameter list that is the goal, and then the sub-parameter in the iteration itself.

## Parameters

- **obj**: Diagnostics object
- **parameterName**: Complex parameter
- **iteration**: Number of the iteration (beginning with 0)
- **subParameter**: Sub parameter
- **numValue**: New numeric value (only possible with numeric parameters)
- **symbValue**: Symbolic value (possible with all parameters)
- **valueIn**: Depending on the [mode](../CAPLfunctionsDiagnosticsAccessMode.md) the value is numerical or symbolical.
- **[mode](../CAPLfunctionsDiagnosticsAccessMode.md)**: Access mode

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

See [on diagRequest](../EventProcedures/CAPLfunctionOnDiagRequest.md)
