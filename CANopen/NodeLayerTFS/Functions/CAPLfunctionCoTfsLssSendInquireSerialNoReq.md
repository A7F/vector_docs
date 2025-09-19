# coTfsLssSendInquireSerialNoRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendInquireSerialNoRequest( dword[] pSerialNo );
```

## Description

This function sends an **Inquire serial number** request and waits for the response.

## Parameters

- **pSerialNo**: Serial number part of the LSS address.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword pSerialNo[1];

/* send LSS inquire serial number request */

if (coTfsLssSendInquireSerialNoRequest( pSerialNo ) == 1) {
  /* sent LSS inquire serial number request and received response */
  /* received value can be found in pSerialNo */
}
```
