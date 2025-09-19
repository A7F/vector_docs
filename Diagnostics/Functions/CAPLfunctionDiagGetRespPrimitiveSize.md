# diagGetRespPrimitiveSize

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagGetRespPrimitiveSize( diagRequest request);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
diagRequest::GetRespPrimitiveSize();
```

## Description

Returns the byte length of the response stored for the request.

## Parameters

- **request**: Request

## Return Values

- **> 0**: Number of bytes
- **< 0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

[diagGetPrimitiveSize](CAPLfunctionDiagGetPrimitiveSize.md)
