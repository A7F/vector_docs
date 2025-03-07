[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssAddMasterResponseConfigureNodeId.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsLssAddMasterResponseConfigureNodeId**

# coTfsLssAddMasterResponseConfigureNodeId (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssAddMasterResponseConfigureNodeId( dword nodeId, dword nodeIdMask, dword errCode, dword specError );
```

## Description

This function adds a single LSS Master request wait condition to the internal list of LSS Master request wait conditions and sends a response if a request is received.

## Parameters

- **nodeId**: Node-ID
- **nodeIdMask**: Mask for node-ID; set bits are compared, not set bits are not compared.
- **errCode**: Error code.
  - 0 - protocol successfully completed
  - 1 - bit timing not supported
  - 255 - implementation specific error occurred
- **specError**: Manufacturer specific error (used if error code = 255).

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)