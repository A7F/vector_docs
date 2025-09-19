# diagCheckValidNegResCode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long diagCheckValidNegResCode(diagRequest obj, dword negResCode);
long diagCheckValidNegResCode(diagResponse obj, dword negResCode);
long diagCheckValidNegResCode(diagResponse obj);
```

## Method Syntax

```c
long diagRequest::CheckValidNegResCode(dword negResCode);
long diagResponse::CheckValidNegResCode(dword negResCode);
long diagResponse::CheckValidNegResCode();
```

## Description

The functions return 1 if the given negative response code is defined for the object. It returns 0 if the code is not valid, and `< 0` for an error. In the one-argument form, the response object has to be a negative response.

## Parameters

- **obj**: Diagnostics object to check the response code for.
- **negResCode**: Negative response code like 0x11, "serviceNotSupported" (KWP 2000).

## Return Values

- **1**: Code is defined for the object in the CDD.
- **0**: Code is not defined for the object in the CDD.

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

[diagGetResponseCode](CAPLfunctionDiagGetResponseCode.md) • [diagGetLastResponseCode](CAPLfunctionDiagGetResponseCode.md)
