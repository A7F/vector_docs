# coTfsLssSendInquireVendorIdRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendInquireVendorIdRequest( dword[] pVendorId );
```

## Description

The function sends an **Inquire vendor-ID request** and waits for the response.

## Parameters

- **pVendorId**: Vendor-ID part of the LSS address.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword pVendorId[1];

/* send LSS inquire vendor ID request */

if (coTfsLssSendInquireVendorIdRequest( pVendorId ) == 1) {
  /* sent LSS inquire vendor ID request and received response */
  /* received value can be found in pVendorId[0] */
}
```
