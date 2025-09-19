# coTfsLssAddMasterResponseSwitchStateSelective (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssAddMasterResponseSwitchStateSelective( dword vendorId, dword vendorIdMask, dword productCode, dword productCodeMask, dword revNo, dword revNoMask, dword serialNo, dword serialNoMask );
```

## Description

This function adds a single LSS Master request wait condition to the internal list of LSS Master request wait conditions and sends a response if a request is received.

## Parameters

- **vendorId**: Vendor-ID part of the LSS address.
- **vendorIdMask**: Mask for vendor-ID part of the LSS address; set bits are compared, not set bits are not compared.
- **productCode**: Product code part of the LSS address.
- **productCodeMask**: Mask for product code part of the LSS address; set bits are compared, not set bits are not compared.
- **revNo**: Revision number part of the LSS address.
- **revNoMask**: Mask for revision number part of the LSS address; set bits are compared, not set bits are not compared.
- **serialNo**: Serial number part of the LSS address.
- **serialNoMask**: Mask for serial number part of the LSS address; set bits are compared, not set bits are not compared.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

---
