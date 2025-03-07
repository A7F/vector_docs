[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssWaitForInquireNodeIdReq.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsLssWaitForInquireNodeIdRequest**

# coTfsLssWaitForInquireNodeIdRequest (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForInquireNodeIdRequest( dword nodeId );
```

## Description

This function waits for the **Inquire node-ID** request and sends the response.

## Parameters

- **nodeId**: New node-ID to be configured, valid values range 1..127 and 255.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* waits for LSS inquire node ID request */
if (coTfsLssWaitForInquireNodeIdRequest( 112 ) == 1) {
  /* received LSS inquire node ID request, sent response with node ID */
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)