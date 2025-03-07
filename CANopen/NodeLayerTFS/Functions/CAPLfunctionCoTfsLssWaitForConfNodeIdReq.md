[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssWaitForConfNodeIdReq.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsLssWaitForConfigureNodeIdRequest

# coTfsLssWaitForConfigureNodeIdRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
long coTfsLssWaitForConfigureNodeIdRequest( byte[] pNID );
```

## Description

The function waits for the configure `LSS node id` request.

## Parameters

- **pNID**: Node-ID of the device, value range 1..127 and 255.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```c
dword pNID[1];

/* waits for LSS configure node ID request */
if (coTfsLssWaitForConfigureNodeIdRequest( pNID) == 1) {
  /* received LSS configure node ID request */
  /* received values can be found in pNID[0] */
} else {
  /* no request received */
  return;
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)