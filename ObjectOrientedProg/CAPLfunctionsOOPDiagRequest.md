[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ObjectOrientedProg/CAPLfunctionsOOPDiagRequest.md)

## Class: DiagRequest

[CAPL Functions](../CAPLfunctions.md) » [Classes](CAPLfunctionsOOPClassesObjects.md) » DiagRequest

Valid for: CANoe DE

This class represents a diagnostic request.

**Note:** The methods are linked to the description of the corresponding CAPL function.

### Function Syntax

- `diagRequest ECUqualifier.serviceIdentifier objectName;`  
  Form 1, Syntax with ECU Qualifier in DiagRequest/Response Objects

- `diagRequest serviceIdentifier objectName;`  
  Form 2, deprecated

**Examples:**

- `diagRequest Door.defaultSessionStart req;`
- `diagRequest defaultSessionStart req;`

### Constructor

—

### Destructor

—

### Method Syntax

- [CheckValidNegResCode](../Diagnostics/Functions/CAPLfunctionDiagCheckValidNegrescode.md)
- [CheckValidPrimitive](../Diagnostics/Functions/CAPLfunctionDiagCheckValidPrimitive.md)
- [CheckValidRespPrimitive](../Diagnostics/Functions/CAPLfunctionDiagCheckValidRespPrimitive.md)
- [GetComplexParameter](../Diagnostics/Functions/CAPLfunctionDiagGetComplexParameter.md)
- [GetComplexParameterRaw, SetComplexParameterRaw](../Diagnostics/Functions/CAPLfunctionDiagGetComplexParameterRaw.md)
- [GetComplexRespParameter](../Diagnostics/Functions/CAPLfunctionDiagGetComplexRespParameter.md)
- [GetComplexRespParameterRaw](../Diagnostics/Functions/CAPLfunctionDiagGetComplexRespParameterRaw.md)
- [GetIterationCount, GetRespIterationCount](../Diagnostics/Functions/CAPLfunctionDiagGetIterationCount.md)
- [GetLastResponse](../Diagnostics/Functions/CAPLfunctionDiagGetLastResponse.md)
- [GetLastResponseCode](../Diagnostics/Functions/CAPLfunctionDiagGetResponseCode.md)
- [GetObjectName](../Diagnostics/Functions/CAPLfunctionDiagGetObjectName.md)
- [GetObjectPath](../Diagnostics/Functions/CAPLfunctionDiagGetObjectPath.md)
- [GetParameter](../Diagnostics/Functions/CAPLfunctionDiagGetParameter.md)
- [GetParameterName](../Diagnostics/Functions/CAPLfunctionDiagGetParameterName.md)
- [GetParameterPath, GetRespParameterPath](../Diagnostics/Functions/CAPLfunctionDiagGetParameterPath.md)
- [GetParameterRaw, SetParameterRaw](../Diagnostics/Functions/CAPLfunctionDiagSetParameterRaw.md)
- GetParameterSize (deprecated)
- [GetParameterType, GetRespParameterType](../Diagnostics/Functions/CAPLfunctionDiagGetParameterType.md)
- [GetParameterUnit](../Diagnostics/Functions/CAPLfunctionDiagGetParameterUnit.md)
- [GetPrimitiveByte](../Diagnostics/Functions/CAPLfunctionDiagGetPrimitiveByte.md)
- [GetPrimitiveData, SetPrimitiveData](../Diagnostics/Functions/CAPLfunctionDiagGetPrimitiveData.md)
- [GetPrimitiveSize](../Diagnostics/Functions/CAPLfunctionDiagGetPrimitiveSize.md)
- [GetRespParameter](../Diagnostics/Functions/CAPLfunctionDiagGetRespParameter.md)
- [GetRespParameterRaw](../Diagnostics/Functions/CAPLfunctionDiagGetRespParameterRaw.md)
- [GetRespPrimitiveByte](../Diagnostics/Functions/CAPLfunctionDiagGetRespPrimitiveByte.md)
- [GetRespPrimitiveSize](../Diagnostics/Functions/CAPLfunctionDiagGetRespPrimitiveSize.md)
- [GetSuppressResp, SetSuppressResp](../Diagnostics/Functions/CAPLfunctionDiagGetSuppressRespDiagSetSuppressResp.md)
- [IsParameterConstant, IsRespParameterConstant](../Diagnostics/Functions/CAPLfunctionDiagIsParameterConstant.md)
- [IsParameterDefault](../Diagnostics/Functions/CAPLfunctionDiagIsParameterDefault.md)
- [IsRespParameterDefault](../Diagnostics/Functions/CAPLfunctionDiagIsRespParameterDefault.md)
- [IsRaw](../Diagnostics/Functions/CAPLfunctionDiagIsRaw.md)
- [IsRawResp](../Diagnostics/Functions/CAPLfunctionDiagIsRawResp.md)
- [ResetParameter](../Diagnostics/Functions/CAPLfunctionDiagResetParameter.md)
- [Resize](../Diagnostics/Functions/CAPLfunctionDiagResize2.md)
- SendMarked (deprecated)
- [SendNegativeResponse](../Diagnostics/Functions/CAPLfunctionDiagSendNegativeResponse.md)
- SendNetwork (deprecated)
- [SendRequest](../Diagnostics/Functions/CAPLfunctionDiagSendRequest.md)
- [SetComplexParameter](../Diagnostics/Functions/CAPLfunctionDiagSetComplexParameter.md)
- [SetParameter](../Diagnostics/Functions/CAPLfunctionDiagSetParameter.md)
- [SetPrimitiveByte](../Diagnostics/Functions/CAPLfunctionDiagSetPrimitiveByte.md)
- [SetRespPrimitiveByte](../Diagnostics/Functions/CAPLfunctionDiagSetRespPrimitiveByte.md)
- [SetSuppressResp](../Diagnostics/Functions/CAPLfunctionDiagGetSuppressRespDiagSetSuppressResp.md)
- [SetTimeoutHandler](../Diagnostics/Functions/CAPLfunctionDiagSetTimeoutHandler.md)

[Diagnostics CAPL Functions](../Diagnostics/CAPLfunctionsDiagnosticsOverview.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
