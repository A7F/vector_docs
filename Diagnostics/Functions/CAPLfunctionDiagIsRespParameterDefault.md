[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagIsRespParameterDefault.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagIsRespParameterDefault

# diagIsRespParameterDefault

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagIsRespParameterDefault (diagRequest obj, char parameterName[])
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
diagRequest::IsRespParameterDefault (char parameterName[])
```

## Description

Access/check a response parameter for a given request. It is not necessary to declare the response and retrieve the response explicitly e.g. via [diagGetLastReponse(diagRequest)](CAPLfunctionDiagGetLastResponse.md) to make a check with [diagResponse.IsParameterDefault("MyParamName")](CAPLfunctionDiagIsParameterDefault.md).

## Parameters

- **obj**: Diagnostics request
- **parameterName**: Parameter qualifier

## Return Values

- **0**: The parameter has none or not its default value.
- **1**: The parameter has its default value.
- **<0**: Diagnostic [Error code](../CAPLfunctionsDiagnosticsErrorCode.md).

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)