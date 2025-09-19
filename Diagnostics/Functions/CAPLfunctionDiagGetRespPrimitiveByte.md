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
