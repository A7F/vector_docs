# diagIsRaw

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```c
long diagIsRaw(diagRequest request);
long diagIsRaw(diagResponse response);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```c
diagRequest::IsRaw();
diagResponse::IsRaw();
```

## Description

Returns if the object is stored as raw data or can be interpreted.

## Parameters

- **request**: Request
- **response**: Response

## Return Values

- **1**: Object is stored as raw data.
- **0**: Object can be interpreted.
- **<0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

[diagIsRawResp](CAPLfunctionDiagIsRawResp.md)
