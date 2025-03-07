[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsDeactivateHeartbeatMonitor.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsDeactivateHeartbeatMonitor**

# coTfsDeactivateHeartbeatMonitor

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsDeactivateHeartbeatMonitor( dword nodeId );
```

## Description

This function switches off the calling of the heartbeat callbacks if these are switched on. The callbacks can be switched on with [coTfsActivateHeartbeatMonitor](CAPLfunctionCoTfsActivateHeartbeatMonitor.md).

## Parameters

- **nodeId**: Identifier of the node for which the heartbeat callbacks are to deactivate.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsActivateHeartbeatMonitor(0x1,100.20);
TestWaitForTimeout(2000);
coTfsDeactivateHeartbeatMonitor(0x1);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)