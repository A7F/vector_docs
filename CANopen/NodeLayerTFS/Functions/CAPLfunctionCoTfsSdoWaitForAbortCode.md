[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoWaitForAbortCode.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsSDOWaitForAbortCode

# coTfsSDOWaitForAbortCode (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDOWaitForAbortCode( dword nodeID );
```

## Description

This function waits until either a SDO abort message was received by the selected DUT (Device Under Test) or a time-out has occurred. After this, the abort code can be read out with [coTfsSDOGetAbortCode](CAPLfunctionCoTfsSdoGetAbortCode.md).

## Parameters

- **nodeID**: Node-ID

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if ( coTfsSDOWaitForAbortCode(2) == 1) {
  write("SDO abort message received, use coTfsSdoGetAbortCode to retrieve its data");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)