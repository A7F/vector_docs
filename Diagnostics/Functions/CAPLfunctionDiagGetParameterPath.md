# diagGetParameterPath, diagGetRespParameterPath

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetParameterPath( diagResponse object, dword paramNo, char[] buffer, dword bufferSize)`
- `long diagGetParameterPath( diagRequest object, dword paramNo, char[] buffer, dword bufferSize)`
- `long diagGetRespParameterPath( diagRequest object, dword paramNo, char[] buffer, dword bufferSize)`

## Method Syntax

- `long diagResponse::GetParameterPath( dword paramNo, char[] buffer, dword bufferSize)`
- `long diagRequest::GetParameterPath( dword paramNo, char[] buffer, dword bufferSize)`
- `long diagRequest::GetRespParameterPath( dword paramNo, char[] buffer, dword bufferSize)`

## Description

Returns the full qualifier path of the parameter at the given position in the primitive. Only leaf parameters that have a simple value are counted, i.e. structural parameters like container lists are NOT returned.

## Parameters

- **object**: Diagnostics object
- **paramNo**: Which leaf parameter in the object, beginning with **0**. Structural parameters are NOT counted.
- **buffer**: Input/output buffer
- **bufferSize**: Buffer size

## Return Values

- Length of path written to buffer, may be truncated.
- [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

See [diagGetObjectPath](CAPLfunctionDiagGetObjectPath.md)

[diagGetParameterLongName, diagGetRespParameterLongName](CAPLfunctiondiagGetParameterLongName.md)
