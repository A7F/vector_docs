[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagResize2.md)

**CAPL Functions** » **Diagnostics** » **diagResize**

# diagResize

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagResize (diagResponse obj)`
- `long diagResize (diagRequest obj)`
- `long diagResize (diagResponse obj, dword byteCount)`
- `long diagResize (diagRequest obj, dword byteCount)`

## Method Syntax

- `diagResponse::Resize()`
- `diagRequest::Resize()`
- `diagResponse::Resize (dword byteCount)`
- `diagRequest::Resize (dword byteCount)`

## Description

Adapt size of a diagnostic object to match specified parameter iterations, or set size of bus message to given number of byte.

## Parameters

- **obj**: Diagnostics object
- **byteCount**: Length of data to send.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

See [on diagRequest](../EventProcedures/CAPLfunctionOnDiagRequest.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)