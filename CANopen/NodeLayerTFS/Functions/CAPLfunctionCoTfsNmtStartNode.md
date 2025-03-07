[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsNmtStartNode.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsNmtStartNode

# coTfsNmtStartNode (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsNmtStartNode( void );
long coTfsNmtStartNode( dword broadcastFlag );
```

## Description

This call triggers a NMT message that sets the DUT (Device Under Test) into the operational state. The set state is checked with heartbeat and guarding mechanisms.

For this, there is first an attempt to configure a heartbeat producer in the DUT (object 0x1017). The heartbeat message contains the current device status. If the DUT should not make a heartbeat producer available, a remote guarding frame is sent to the DUT. The DUT responds with the corresponding guarding response. The procedure is repeated again. The second response is evaluated and contains the device status. The CANopen® specification provides that a CANopen® device supports at least one of the two modes.

**Note:** If the heartbeat producer is already active, it will be restored at the end.

## Parameters

- **broadcastFlag**: `!=0`: NMT message is sent to all nodes (broadcast)

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if ( coTfsNmtStartNode() != 1) {
  write("start node failed");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)