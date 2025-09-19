[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetParameterCoded.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetParameterCoded, diagSetParameterCoded

# diagGetParameterCoded, diagSetParameterCoded

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long diagGetParameterCoded(diagResponse obj, char parameterName[], byte* buffer, dword bufferSize);
long diagGetParameterCoded(diagRequest obj, char parameterName[], byte* buffer, dword bufferSize);
long diagSetParameterCoded(diagResponse obj, char parameterName[], byte* buffer, dword bufferSize);
long diagSetParameterCoded(diagRequest obj, char parameterName[], byte* buffer, dword bufferSize);
```

## Description

Sets or specifies the value of a parameter directly via coded data bytes.

## Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier (NOT the language-dependent name of the parameter!)
- **buffer**: Input buffer
- **bufferSize**: Buffer size

## Return Values

0 if bytes were copied, otherwise <0 for an [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)