[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagSetPrimitiveByte.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagSetPrimitiveByte

# diagSetPrimitiveByte

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagSetPrimitiveByte( diagRequest request, DWORD bytePos, DWORD newValue);
long diagSetPrimitiveByte( diagResponse response, DWORD bytePos, DWORD newValue);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
diagRequest::SetPrimitiveByte( DWORD bytePos, DWORD newValue);
diagResponse::SetPrimitiveByte( DWORD bytePos, DWORD newValue);
```

## Description

Writes one byte of a diagnostic object.

## Parameters

- **request**: Request
- **response**: Response
- **bytePos**: Zero-based position of the byte in the object
- **newValue**: New value of the accessed byte

## Return Values

- **≥ 0**: Requested value or "no error"
- **< 0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

[diagSetRespPrimitiveByte](CAPLfunctionDiagSetRespPrimitiveByte.md) • [diagGetPrimitiveByte](CAPLfunctionDiagGetPrimitiveByte.md) • [diagGetRespPrimitiveByte](CAPLfunctionDiagGetRespPrimitiveByte.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)