[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssSendConfNodeIdReq.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsLssSendConfigureNodeIdRequest**

# coTfsLssSendConfigureNodeIdRequest (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendConfigureNodeIdRequest( dword NID, byte[] pErrorCode, byte[] pSpecificError );
```

## Description

This function sends a configure **LSS configure node-ID** request and waits for the response.

## Parameters

- **NID**: node-ID of the device under test (DUT), value range 1..127 and 255
- **pErrorCode**: error code
  - 0 - protocol successfully completed
  - 1 - node-ID out of range
  - 255 - implementation specific error occurred
- **pSpecificError**: manufacturer specific error (used if error code = 255)

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
byte pErrorCode[1];
byte pSpecificError[1];

/* send LSS configure nodeID request and wait for response */

if (coTfsLssSendConfigureNodeIdRequest( 112 , pErrorCode, pSpecificError) == 1) {
    /* request sent and DUT replied with correct response. Response values can be found in pErrorCode, pSpecificError */
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)