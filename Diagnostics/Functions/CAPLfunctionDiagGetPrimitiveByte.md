[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetPrimitiveByte.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetPrimitiveByte

# diagGetPrimitiveByte

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diagGetPrimitiveByte( diagRequest request, DWORD bytePos);
long diagGetPrimitiveByte( diagResponse response, DWORD bytePos);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
diagRequest::GetPrimitiveByte( DWORD bytePos);
diagResponse::GetPrimitiveByte( DWORD bytePos);
```

## Description

Reads one byte of a diagnostic object.

## Parameters

- **request**: Request
- **response**: Response
- **bytePos**: Zero-based position of the byte in the object

## Return Values

- **≥ 0**: Requested value or "no error"
- **< 0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

[diag GetRespPrimitiveByte](CAPLfunctionDiagGetRespPrimitiveByte.md) • [diagSetPrimitiveByte](CAPLfunctionDiagSetPrimitiveByte.md) • [diagSetRespPrimitiveByte](CAPLfunctionDiagSetRespPrimitiveByte.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)