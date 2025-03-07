[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagCheckValidNegrescode.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagCheckValidNegResCode

# diagCheckValidNegResCode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagCheckValidNegResCode( diagRequest obj, dword negResCode);`
- `long diagCheckValidNegResCode( diagResponse obj, dword negResCode);`
- `long diagCheckValidNegResCode( diagResponse obj);`

## Method Syntax

- `long diagRequest::CheckValidNegResCode(dword negResCode);`
- `long diagResponse::CheckValidNegResCode(dword negResCode);`
- `long diagResponse::CheckValidNegResCode();`

## Description

The functions return 1 if the given negative response code is defined for the object. It returns 0 if the code is not valid, and <0 for an error. In the one-argument form, the response object has to be a negative response.

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)