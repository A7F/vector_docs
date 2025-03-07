[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagResetParameter.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagResetParameter

# diagResetParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagResetParameter (diagResponse obj, char parameterName[])`
- `long diagResetParameter (diagRequest obj, char parameterName[])`

## Method Syntax

- `diagResponse::ResetParameter (char parameterName[])`
- `diagRequest::ResetParameter (char parameterName[])`

## Description

Sets the parameter to its default value.

## Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)