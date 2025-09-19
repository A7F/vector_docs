# _Diag_PhysicalRequest, _Diag_FunctionalRequest

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void _Diag_PhysicalRequest(char target[], byte rawRequest[]);
void _Diag_FunctionalRequest(char target[], byte rawRequest[]);
```

## Description

The given bytes shall be sent as a **physical** or **functional** diagnostic request to the ECU or functional group with the given qualifier.

## Parameters

- **target**: Qualifier of the ECU or functional group to send to.
- **rawRequest**: Bytes of the raw request that shall be sent.

## Return Values

—

## Example

—

[_Diag_DataRequest](CAPLfunctionDiagDataRequest.md)
