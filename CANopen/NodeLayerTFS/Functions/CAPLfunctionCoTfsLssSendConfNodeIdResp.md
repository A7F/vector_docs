[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssSendConfNodeIdResp.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsLssSendConfigureNodeIdResponse**

# coTfsLssSendConfigureNodeIdResponse (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendConfigureNodeIdResponse( dword errorCode, dword specificError );
```

## Description

This function sends the **LSS configure node-ID** response.

## Parameters

- **errorCode**  
  Error code.
  - 0 - protocol successfully completed
  - 1 - node-ID out of range
  - 255 - implementation specific error occurred

- **specificError**  
  Manufacturer specific error (used if error code = 255).

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* send LSS configure nodeID response */

if (coTfsLssSendConfigureNodeIdResponse( 0, 0 ) != 1) {
  /* message could not be sent */
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)