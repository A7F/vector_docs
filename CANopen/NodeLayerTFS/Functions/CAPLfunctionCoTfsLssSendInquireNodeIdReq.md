[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssSendInquireNodeIdReq.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsLssSendInquireNodeIdRequest

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)