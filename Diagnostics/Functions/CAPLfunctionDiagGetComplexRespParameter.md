[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetComplexRespParameter.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetComplexRespParameter

# diagGetComplexRespParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

The behavior of this CAPL function depends on the used parameters.

Possible scenarios:

## Retrieve the value of a numeric complex parameter

### Function Syntax

```plaintext
long diagGetComplexRespParameter (diagRequest req, char parameterName[], dword iteration, char subParameter[], double output[]);
long diagGetComplexRespParameter (diagRequest req, long mode, char parameterName[], dword iteration, char subParameter[], double output[]);
```

### Method Syntax

```plaintext
long diagRequest::GetComplexRespParameter (char parameterName[], dword iteration, char subParameter[], double output[]);
long diagRequest::GetComplexRespParameter (long mode, char parameterName[], dword iteration, char subParameter[], double output[]);
```

### Description

Returns the value of a numeric complex parameter. This function offers access to parameters contained in a received response object, whereby the function is addressed directly by the request. This eliminates the need to generate a separate response object. If no response is available yet for the request, an error is reported.

### Parameters

- **req**: Request
- **parameterName**: Parameter qualifier
- **iteration**: Iteration (beginning with 0)
- **subParameter**: Sub parameter qualifier
- **output**: Output field. If given, `output` contains the value of the parameter after return of this method.
- **mode**: Switch the representation of the transmitted value according to the given [mode](../CAPLfunctionsDiagnosticsAccessMode.md).

### Return Values

- [Error code](../CAPLfunctionsDiagnosticsErrorCode.md),
- or value of the parameter or 0.0 if this could not be acquired.

### Example

[Using Diagnostics Functions in Test Cases](../CAPLfunctionsDiagnosticsUsingFunctionTestCase.md)

## Retrieve the symbolic value of a complex parameter

### Function Syntax

```plaintext
long diagGetComplexRespParameter (diagRequest req, char parameterName[], dword iteration, char subParameter[], char buffer[], dword bufferLen);
```

### Method Syntax

```plaintext
diagRequest::GetComplexRespParameter (char parameterName[], dword iteration, char subParameter[], char buffer[], dword bufferLen);
```

### Description

Returns the symbolic value of a complex parameter. This is possible for all parameters. This function offers access to parameters contained in a received response object, whereby the function is addressed directly by the request. This eliminates the need to generate a separate response object. If no response is available yet for the request, an error is reported.

### Parameters

- **req**: Request
- **parameterName**: Parameter qualifier
- **iteration**: Iteration (beginning with 0)
- **subParameter**: Sub parameter qualifier
- **buffer**: Output buffer
- **bufferLen**: Buffer size

### Return Values

- [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

### Example

[Using Diagnostics Functions in Test Cases](../CAPLfunctionsDiagnosticsUsingFunctionTestCase.md)

## Retrieve the numeric sub-parameter from a parameter iteration directly

### Function Syntax

```plaintext
double diagGetComplexRespParameter (diagRequest req, char parameterName[], dword iteration, char subParameter[]);
double diagGetComplexRespParameter (diagRequest req, long mode, char parameterName[], dword iteration, char subParameter[]);
```

### Method Syntax

```plaintext
diagRequest::GetComplexRespParameter (char parameterName[], dword iteration, char subParameter[]);
diagRequest::GetComplexRespParameter (long mode, char parameterName[], dword iteration, char subParameter[]);
```

### Description

Retrieve numeric sub-parameter from a parameter iteration directly. This function offers access to parameters contained in a received response object, whereby the function is addressed directly by the request. This eliminates the need to generate a separate response object. If no response is available yet for the request, an error is reported.

### Parameters

- **req**: Request
- **parameterName**: Parameter qualifier
- **iteration**: Iteration (beginning with 0)
- **subParameter**: Sub parameter qualifier
- **mode**: Switch the representation of the transmitted value according to the given [mode](../CAPLfunctionsDiagnosticsAccessMode.md).

### Return Values

- Parameter value.

### Example

[Using Diagnostics Functions in Test Cases](../CAPLfunctionsDiagnosticsUsingFunctionTestCase.md)

[diagGetComplexParameter](CAPLfunctionDiagGetComplexParameter.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)