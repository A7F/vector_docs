[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssWaitForSwitchStateModeGlobalMsgReq.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsLssWaitForSwitchStateModeGlobalRequest

# coTfsLssWaitForSwitchStateModeGlobalRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForSwitchStateModeGlobalRequest( byte[] pMode );
```

## Description

This function waits for a **LSS switch state global mode** request.

## Parameters

- **pMode**: 
  - 0 - waiting mode
  - 1 - configuration mode

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
byte pMode[1];

/* waits for LSS switch state global request */
if (coTfsLssWaitForSwitchStateModeGlobalRequest() == 1) {
  /* received LSS switch state global request */
  /* value in pMode[0] */
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)