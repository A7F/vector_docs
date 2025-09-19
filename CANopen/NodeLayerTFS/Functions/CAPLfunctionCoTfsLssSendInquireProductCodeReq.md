# coTfsLssSendInquireProductCodeRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendInquireProductCodeRequest( dword[] pProductCode );
```

## Description

This function sends an **Inquire product code** request and waits for the response.

## Parameters

- **pProductCode**: Product code part of the LSS address.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword pProductCode[1];

/* send LSS inquire product code request */

if (coTfsLssSendInquireProductCodeRequest( pProductCode ) == 1) {
  /* sent LSS inquire product code request and received response */
  /* received value can be found in pProductCode */
}
```
