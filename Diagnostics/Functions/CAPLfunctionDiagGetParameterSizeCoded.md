[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetParameterSizeCoded.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetParameterSizeCoded

# diagGetParameterSizeCoded

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetParameterSizeCoded(diagRequest obj, char parameterName[])`
- `long diagGetParameterSizeCoded(diagResponse obj, char parameterName[])`

## Method Syntax

- `diagRequest::GetParameterSizeCoded(char* parameterName);`
- `diagResponse::GetParameterSizeCoded(char* parameterName);`

## Description

Returns the length of the coded parameter in bits.

## Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier

## Return Values

If > 0 the number of bits, otherwise an [error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)