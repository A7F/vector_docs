# coTfsLssAddMasterResponseStoreConfiguration (Level 2)

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssAddMasterResponseStoreConfiguration( dword errCode, dword specError );
```

## Description

This function adds a single LSS Master request wait condition to the internal list of LSS Master request wait conditions and sends a response if a request is received.

## Parameters

- **errCode**: Error code.
  - 0 - protocol successfully completed
  - 1 - bit timing not supported
  - 255 - implementation specific error occurred

- **specError**: Manufacturer specific error (used if error code = 255).

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)
