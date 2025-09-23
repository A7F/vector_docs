[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ObjectOrientedProg/CAPLfunctionsOOPDiagResponse.md)

## Class: DiagResponse

[CAPL Functions](../CAPLfunctions.md) » [Classes](CAPLfunctionsOOPClassesObjects.md) » DiagResponse

This class represents a diagnostic response.

**Note**  
The methods are linked to the description of the corresponding CAPL function.

### Function Syntax

- `diagResponse ECUQualifier.serviceIdentifier objectName;`  
  Form 1, Syntax with ECU Qualifier in DiagRequest/Response Objects

- `diagResponse serviceIdentifier objectName;`  
  Form 2 (deprecated)

**Examples:**

- `diagResponse Door.defaultSessionStart resp;`
- `diagResponse this resp;`
- `diagResponse defaultSessionStart resp;`

### Constructor

[Constructor](../../Shared/CAPL/General/ClassesAndObjects.md)

### Destructor

[Destructor](../../Shared/CAPL/General/ClassesAndObjects.md)

### Method Syntax

- [CheckValidNegResCode](../Diagnostics/Functions/CAPLfunctionDiagCheckValidNegrescode.md)
- [CheckValidPrimitive](../Diagnostics/Functions/CAPLfunctionDiagCheckValidPrimitive.md)
- [GetComplexParameter](../Diagnostics/Functions/CAPLfunctionDiagGetComplexParameter.md)
- [GetComplexParameterRaw, SetComplexParameterRaw](../Diagnostics/Functions/CAPLfunctionDiagGetComplexParameterRaw.md)
- [GetComplexRespParameterRaw](../Diagnostics/Functions/CAPLfunctionDiagGetComplexRespParameterRaw.md)
- [GetIterationCount](../Diagnostics/Functions/CAPLfunctionDiagGetIterationCount.md)
- [GetLastResponse](../Diagnostics/Functions/CAPLfunctionDiagGetLastResponse.md)
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
- [GetResponseCode](../Diagnostics/Functions/CAPLfunctionDiagGetResponseCode.md)
- [GetSendingMode](../Diagnostics/Functions/CAPLfunctionDiagGetSendingMode.md)
- [IsNegativeResponse](../Diagnostics/Functions/CAPLfunctionDiagIsNegativeResponse.md)
- [IsParameterConstant](../Diagnostics/Functions/CAPLfunctionDiagIsParameterConstant.md)
- [IsParameterDefault](../Diagnostics/Functions/CAPLfunctionDiagIsParameterDefault.md)
- [IsPositiveResponse](../Diagnostics/Functions/CAPLfunctionDiagIsPositiveResponse.md)
- [IsRaw](../Diagnostics/Functions/CAPLfunctionDiagIsRaw.md)
- [ResetParameter](../Diagnostics/Functions/CAPLfunctionDiagResetParameter.md)
- [Resize](../Diagnostics/Functions/CAPLfunctionDiagResize2.md)
- [SendNegativeResponse](../Diagnostics/Functions/CAPLfunctionDiagSendNegativeResponse.md)
- [SendPositiveResponse](../Diagnostics/Functions/CAPLfunctionDiagSendResponse.md)
- [SendResponse](../Diagnostics/Functions/CAPLfunctionDiagSendResponse.md)
- [SetComplexParameter](../Diagnostics/Functions/CAPLfunctionDiagSetComplexParameter.md)
- [SetParameter](../Diagnostics/Functions/CAPLfunctionDiagSetParameter.md)
- [SetPrimitiveByte](../Diagnostics/Functions/CAPLfunctionDiagSetPrimitiveByte.md)

[Declaration and Initialization of Diagnostic Objects](../../CANoeCANalyzer/Diagnostics/Analysis/DiagnosticsDiagnosticsObjectsInCAPL.md) • [Diagnostics CAPL Functions](../Diagnostics/CAPLfunctionsDiagnosticsOverview.md)

---
