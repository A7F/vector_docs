# coTfsLssSendSwitchStateSelectiveSequence (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendSwitchStateSelectiveSequence( dword vendorId, dword productCode, dword revisionNo, dword serialNo );
```

## Description

The function sends a switch state selective messages and waits for the response.

## Parameters

- **vendorId**: Vendor-ID part of the LSS address.
- **productCode**: Product code part of the LSS address.
- **revisionNo**: Revision number part of the LSS address.
- **serialNo**: Serial number part of the LSS address.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* send LSS switch state selective protocol request */

if (coTfsLssSendSwitchStateSelectiveSequence( 0x12345678,  0x11223344, 0x87654321, 0x1) != 1) {
  /* message could not be sent */
}
```
