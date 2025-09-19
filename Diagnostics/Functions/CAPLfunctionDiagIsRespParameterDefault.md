# diagIsRespParameterDefault

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long diagIsRespParameterDefault(diagRequest obj, char parameterName[]);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```c
diagRequest::IsRespParameterDefault(char parameterName[]);
```

## Description

Access/check a response parameter for a given request. It is not necessary to declare the response and retrieve the response explicitly e.g. via [diagGetLastReponse(diagRequest)](CAPLfunctionDiagGetLastResponse.md) to make a check with [diagResponse.IsParameterDefault("MyParamName")](CAPLfunctionDiagIsParameterDefault.md).

## Parameters

- **obj**: Diagnostics request
- **parameterName**: Parameter qualifier

## Return Values

- **0**: The parameter has none or not its default value.
- **1**: The parameter has its default value.
- **`< 0`**: Diagnostic [Error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

```plaintext
testfunction MainTest()
{
   diagRequest DefaultSession_Start req;
   diagSetTarget("Door");
   diagSendRequest(req);
   testWaitForDiagResponse(req, 2000);
   write("IsDefault(P3) = %d", diagIsRespParameterDefault(req, "P3"));
}
```
