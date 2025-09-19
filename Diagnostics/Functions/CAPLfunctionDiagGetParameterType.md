# diagGetParameterType, diagGetRespParameterType

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetParameterType(diagResponse object, char[] qualifier, char[] buffer, DWORD bufferSize)`
- `long diagGetParameterType(diagRequest object, char[] qualifier, char[] buffer, DWORD bufferSize)`
- `long diagGetRespParameterType(diagRequest object, char[] qualifier, char[] buffer, DWORD bufferSize)`

## Method Syntax

- `diagResponse::GetParameterType(char[] qualifier, char[] buffer, DWORD bufferSize)`
- `diagRequest::GetParameterType(char[] qualifier, char[] buffer, DWORD bufferSize)`
- `diagRequest::GetRespParameterType(char[] qualifier, char[] buffer, DWORD bufferSize)`

## Description

Retrieve the qualifier of the parameter's type.

## Parameters

- **object**: Diagnostics object
- **qualifier**: Parameter qualifier
- **buffer**: Input/output buffer
- **bufferSize**: Buffer size

## Return Values

- Length of qualifier written to buffer, may be truncated.
- [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—
