[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetRespParameter.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetRespParameter

# diagGetRespParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

The behavior of this CAPL function depends on the used parameters.

Possible scenarios:

## Retrieves the value of the numeric parameter

### Function Syntax

- `long diagGetRespParameter (diagRequest req, char parameterName[], double output[]);`
- `long diagGetRespParameter (diagRequest req, long mode, char parameterName[], double output[]);`

### Method Syntax

- `diagRequest::GetRespParameter (char parameterName[], double output[]);`
- `diagRequest::GetRespParameter (long mode, char parameterName[], double output[]);`

### Description

Returns the value of the numeric parameter, either in an output field or as return value (without the possibility of checking the correct function).

This function offers access to parameters contained in a received response object, whereby the function is addressed directly by the request. This eliminates the need to generate a separate response object. If no response is available yet for the request, an error is reported.

### Parameters

- **req**: Request
- **parameterName**: Parameter qualifier
- **output**: Output field
- **[mode](../CAPLfunctionsDiagnosticsAccessMode.md)**: Access mode

### Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md) or value of the parameter.

### Example

[Using Diagnostics Functions in Test Cases](../CAPLfunctionsDiagnosticsUsingFunctionTestCase.md)

## Retrieves the symbolic value of the parameter

### Function Syntax

- `long diagGetRespParameter (diagRequest req, char parameterName[], char buffer[], dword bufferLen);`

### Method Syntax

- `diagRequest::GetRespParameter (char parameterName[], char buffer[], dword bufferLen);`

### Description

Returns the symbolic value of the parameter. This functions for all parameters. The values received can be used for setting the parameter.

This function offers access to parameters contained in a received response object, whereby the function is addressed directly by the request. This eliminates the need to generate a separate response object. If no response is available yet for the request, an error is reported.

### Parameters

- **req**: Request
- **parameterName**: Parameter qualifier
- **buffer**: Output field
- **bufferLen**: Size of the buffer

### Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

### Example

[Using Diagnostics Functions in Test Cases](../CAPLfunctionsDiagnosticsUsingFunctionTestCase.md)

## Retrieves the numeric parameter directly

### Function Syntax

- `double diagGetRespParameter (diagRequest req, char parameterName[]);`
- `double diagGetRespParameter (diagRequest req, long mode, char parameterName[]);`

### Method Syntax

- `diagRequest::GetRespParameter (char parameterName[]);`
- `diagRequest::GetRespParameter (long mode, char parameterName[]);`

### Description

Retrieves numeric parameter directly.

This function offers access to parameters contained in a received response object, whereby the function is addressed directly by the request. This eliminates the need to generate a separate response object. If no response is available yet for the request, an error is reported.

### Parameters

- **req**: Request
- **parameterName**: Parameter qualifier
- **[mode](../CAPLfunctionsDiagnosticsAccessMode.md)**: Access mode

### Return Values

Parameter value

### Example

[Using Diagnostics Functions in Test Cases](../CAPLfunctionsDiagnosticsUsingFunctionTestCase.md)

[diagGetParameter](CAPLfunctionDiagGetParameter.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)