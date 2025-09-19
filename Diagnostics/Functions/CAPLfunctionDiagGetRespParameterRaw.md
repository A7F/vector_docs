# diagGetRespParameterRaw

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagGetRespParameterRaw (diagRequest req, char parameterName[], byte buffer[], dword bufferLen);
```

## Method Syntax

```
diagRequest::GetRespParameterRaw (char parameterName[], byte buffer[], dword bufferLen);
```

## Description

This function offers access to parameters contained in a received response object, whereby the function is addressed directly by the request. This eliminates the need to generate a separate response object. If no response is available yet for the request, an error is reported.

## Parameters

- **req**: Request
- **parameterName**: Parameter qualifier
- **buffer**: Output field
- **bufferLen**: Size of the buffer

## Return Values

- **0**: if bytes were copied
- **< 0**: otherwise for an [error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

[Using Diagnostics Functions in Test Cases](../CAPLfunctionsDiagnosticsUsingFunctionTestCase.md)
