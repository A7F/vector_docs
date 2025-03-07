[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssSendIdentifySlaveResp.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsLssSendIdentifySlaveResponse**

# coTfsLssSendIdentifySlaveResponse (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendIdentifySlaveResponse( void );
```

## Description

This function sends an **Identify slave protocol response** message.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* sends LSS identify slave protocol response message */

if (coTfsLssSendIdentifySlaveResponse() == 1) {
  /* message sent */
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)