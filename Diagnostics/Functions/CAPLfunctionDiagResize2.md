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
