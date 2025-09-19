# diagSetRespPrimitiveByte

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diagSetRespPrimitiveByte( diagRequest request, 
 DWORD bytePos, DWORD newValue);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
diagRequest::SetRespPrimitiveByte( DWORD bytePos, DWORD newValue);
```

## Description

Writes one byte of the response stored for the request.

## Parameters

- **request**: Request
- **bytePos**: Position of the byte in the object.
- **newValue**: New value of the accessed byte.

## Return Values

- **≥ 0**: Requested value or "no error"
- **< 0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

[diagSetPrimitiveByte](CAPLfunctionDiagSetPrimitiveByte.md) • [diagGetPrimitiveByte](CAPLfunctionDiagGetPrimitiveByte.md) • [diagGetRespPrimitiveByte](CAPLfunctionDiagGetRespPrimitiveByte.md)
