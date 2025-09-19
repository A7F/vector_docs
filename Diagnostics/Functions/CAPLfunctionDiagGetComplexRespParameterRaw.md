# diagGetComplexRespParameterRaw

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long diagGetComplexRespParameterRaw (diagRequest req, char parameterName[], dword iteration, char subParameter[], byte buffer[], dword bufferLen);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
long diagRequest::GetComplexRespParameterRaw (char parameterName[], dword iteration, char subParameter[], byte buffer[], dword bufferLen);
```

## Description

Reads/sets the complex parameter to the specified raw value.

This function offers access to parameters contained in a received response object, whereby the function is addressed directly by the request. This eliminates the need to generate a separate response object. If no response is available yet for the request, an error is reported.

## Parameters

- **req**: Request
- **parameterName**: Parameter qualifier
- **iteration**: Iteration (beginning with 0)
- **subParameter**: Sub parameter qualifier
- **buffer**: Output buffer
- **bufferLen**: Buffer size

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

[Using Diagnostics Functions in Test Cases](../CAPLfunctionsDiagnosticsUsingFunctionTestCase.md)

[diagGetComplexParameterRaw](CAPLfunctionDiagGetComplexParameterRaw.md)
