# diagIsRawResp

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long diagIsRawResp(diagRequest request);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```c
diagRequest::IsRawResp();
```

## Description

Returns if the response stored for the request is stored as raw data or can be interpreted.

## Parameters

- **request**: Request

## Return Values

- **1**: Response is stored as raw data.
- **0**: Response can be interpreted.
- **<0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

[diagIsRaw](CAPLfunctionDiagIsRaw.md)
