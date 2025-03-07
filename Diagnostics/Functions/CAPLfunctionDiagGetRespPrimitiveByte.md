[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetRespPrimitiveByte.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetRespPrimitiveByte

# diagGetRespPrimitiveByte

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diagGetRespPrimitiveByte( diagRequest request, DWORD bytePos);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
diagRequest::GetRespPrimitiveByte( DWORD bytePos);
```

## Description

Reads one byte of the response stored for the request.

## Parameters

- **request**: Request
- **bytePos**: Position of the byte in the response

## Return Values

- **≥ 0**: Requested value or "no error"
- **< 0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

[diagGetPrimitiveByte](CAPLfunctionDiagGetPrimitiveByte.md) • [diagSetPrimitiveByte](CAPLfunctionDiagSetPrimitiveByte.md) • [diagSetRespPrimitiveByte](CAPLfunctionDiagSetRespPrimitiveByte.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)