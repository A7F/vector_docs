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

0 if bytes were copied, otherwise `< 0` for an [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—
