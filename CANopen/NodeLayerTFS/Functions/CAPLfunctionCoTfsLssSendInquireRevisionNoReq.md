[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssSendInquireRevisionNoReq.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsLssSendInquireRevisionNoRequest

# coTfsLssSendInquireRevisionNoRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendInquireRevisionNoRequest( dword[] pRevisionNo );
```

## Description

This function sends an **Inquire revision number** request and waits for the response.

## Parameters

- **pRevisionNo**: Revision number part of the LSS address.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword pRevisionNo[1];

/* send LSS inquire revision number request */

if (coTfsLssSendInquireRevisionNoRequest( pRevisionNo ) == 1) {
  /* sent LSS inquire revision number request and received response */
  /* received value can be found in pRevisionNo */
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)