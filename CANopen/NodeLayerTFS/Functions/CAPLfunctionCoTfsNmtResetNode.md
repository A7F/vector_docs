[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsNmtResetNode.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsNmtResetNode

# coTfsNmtResetNode (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsNmtResetNode( void );
long coTfsNmtResetNode( dword broadcastFlag );
```

## Description

This call triggers a NMT message that resets the DUT (Device Under Test). After sending out the message, the boot-up message of the DUT is awaited. The reliable wait time corresponds to the general wait time, which is set with [coTfsSetTimeoutValue](CAPLfunctionCoTfsSetTimeOutValue.md).

**Note:** If the heartbeat producer is already active, it will be restored at the end.

## Parameters

- **broadcastFlag**: `!=0`: NMT message is sent to all nodes (broadcast)

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if (coTfsNmtResetNode() != 1) {
  write("reset node failed");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)