# diagGetComplexParameterRaw, diagSetComplexParameterRaw

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetComplexParameterRaw (diagResponse obj, char parameterName[], dword iteration, char subParameter[], byte buffer[], dword buffersize)`
- `long diagGetComplexParameterRaw (diagRequest obj, char parameterName[], dword iteration, char subParameter[], byte buffer[], dword buffersize)`
- `long diagSetComplexParameterRaw (diagResponse obj, char parameterName[], dword iteration, char subParameter[], byte buffer[], dword buffersize)`
- `long diagSetComplexParameterRaw (diagRequest obj, char parameterName[], dword iteration, char subParameter[], byte buffer[], dword buffersize)`

## Method Syntax

- `long diagResponse::GetComplexParameterRaw (char parameterName[], dword iteration, char subParameter[], byte buffer[], dword buffersize)`
- `long diagRequest::GetComplexParameterRaw (char parameterName[], dword iteration, char subParameter[], byte buffer[], dword buffersize)`
- `long diagResponse::SetComplexParameterRax (char parameterName[], dword iteration, char subParameter[], byte buffer[], dword buffersize)`
- `long diagRequest::SetComplexParameterRaw (char parameterName[], dword iteration, char subParameter[], byte buffer[], dword buffersize)`

## Description

Reads/sets the complex parameter to the specified raw value.

## Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier
- **iteration**: Iteration (beginning with 0)
- **subParameter**: Sub parameter qualifier
- **buffer**: Output buffer
- **buffersize**: Buffer size

## Return Values

Number of bytes copied into the buffer or [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—
