[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagSetParameterRaw.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagSetParameterRaw, diagGetParameterRaw

# diagSetParameterRaw, diagGetParameterRaw

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `long diagSetParameterRaw (diagResponse obj, char parameter[], byte* buffer, DWORD buffersize); // form 1`
- `long diagSetParameterRaw (diagRequest obj, char parameterName[], byte* buffer, DWORD buffersize); // form 2`
- `long diagGetParameterRaw (diagResponse obj, char parameterName[], byte* buffer, DWORD buffersize); // form 3`
- `long diagGetParameterRaw (diagRequest obj, char parameterName[], byte* buffer, DWORD buffersize); // form 4`

## Method Syntax

- `long diagResponse::SetParameterRaw (char parameterName[], byte* buffer, DWORD buffersize); // form 1`
- `long diagRequest::SetParameterRaw (char parameterName[], byte* buffer, DWORD buffersize); // form 2`
- `long diagResponse::GetParameterRaw (char parameterName[], byte* buffer, DWORD buffersize); // form 3`
- `long diagRequest::GetParameterRaw (char parameterName[], byte* buffer, DWORD buffersize); // form 4`

## Description

Sets or specifies the value of a (complex) parameter directly via uncoded data bytes.

## Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier
- **buffer**: Input/output buffer
- **buffersize**: Buffer size

## Return Values

[error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

See [diagGenerateKeyFromSeed](CAPLfunctionDiagGenerateKeyFromSeed.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)