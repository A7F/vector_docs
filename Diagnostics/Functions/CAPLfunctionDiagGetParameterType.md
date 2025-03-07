[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetParameterType.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetParameterType, diagGetRespParameterType

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)