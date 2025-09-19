# coTfsLssWaitForInquireVendorIdRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForInquireVendorIdRequest( dword vendorId );
```

## Description

This function waits for the **Inquire vendor-ID** request and sends the response.

## Parameters

- **vendorId**: Vendor-ID part of the LSS address.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* waits for LSS inquire vendor ID request */
if (coTfsLssWaitForInquireVendorIdRequest( 0x12345678) == 1) {
  /* received LSS inquire vendor ID request, sent response with vendorId */
}
```
