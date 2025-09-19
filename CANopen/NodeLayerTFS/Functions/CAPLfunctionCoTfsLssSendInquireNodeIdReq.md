# coTfsLssSendInquireNodeIdRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendInquireNodeIdRequest( dword[] pNodeId );
```

## Description

This function sends an **Inquire node-ID** request and waits for the response.

## Parameters

- **pNodeId**: New node-ID to be configured, valid values range 1..127 and 255.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
byte pNodeId[1];

/* send LSS inquire node ID request */

if (coTfsLssSendInquireNodeIdRequest( pNodeId ) == 1) {
  /* sent LSS inquire node ID request and received response */
  /* received value can be found in pNodeId */
}
```

---
