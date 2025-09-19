# coTfsLssAddMasterResponseInquireVendorId (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe:lite DE •  CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssAddMasterResponseInquireVendorId( dword vendorId );
```

## Description

This function adds a single LSS Master request wait condition to the internal list of LSS Master request wait conditions and sends a response if a request is received.

## Parameters

- **vendorId**: Vendor-ID part of the LSS address.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)
