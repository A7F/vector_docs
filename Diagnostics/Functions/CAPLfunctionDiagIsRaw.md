[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagIsRaw.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagIsRaw

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)