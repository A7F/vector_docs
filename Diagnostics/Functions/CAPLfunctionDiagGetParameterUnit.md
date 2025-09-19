# diagGetParameterUnit

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long diagGetParameterUnit (diagResponse obj, char parameterName[], char buffer[], DWORD buffersize)
long diagGetParameterUnit (diagRequest obj, char parameterName[], char buffer[], DWORD buffersize)
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
diagResponse::GetParameterUnit (char parameterName[], char buffer[], DWORD buffersize)
diagRequest::GetParameterUnit (char parameterName[], char buffer[], DWORD buffersize)
```

## Description

Writes the unit of the parameter in the transmitted field.

## Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier
- **buffer**: Output buffer
- **buffersize**: Buffer size

## Return Values

Number of chars written to buffer or [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—
