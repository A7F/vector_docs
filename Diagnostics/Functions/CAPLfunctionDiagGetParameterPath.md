[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetParameterPath.md)

**CAPL Functions** » **Diagnostics** » diagGetParameterPath, diagGetRespParameterPath

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)