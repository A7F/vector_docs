[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetComplexRespParameterRaw.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetComplexRespParameterRaw

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)