[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssSendInquireProductCodeReq.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsLssSendInquireProductCodeRequest

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)