[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsActivateGuardingReqMonitor.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsActivateGuardingReqMonitor

# coTfsActivateGuardingReqMonitor

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsActivateGuardingReqMonitor( dword nodeID, dword guardTime, dword tolerance );
```

## Description

When this function is called, it is checked whether the DUT (Device Under Test) makes available the remote frame for the guarding within the defined times.

For each correct occurrence, the callback `void coTfsOnGuardingRTRMsg(dword nodeId)` is called. If the time is not adhered to, then the callback `void coTfsOnGuardingRTRFail(dword nodeId, dword cause)` is called once. After an error has occurred, the callback system is automatically disabled. The reason for the error is specified in the parameter **cause**:
- 1 = Message distance too small
- 2 = Message distance too large or message is missing

This check can be switched off again with [coTfsDeactivateGuardingReqMonitor](CAPLfunctionCoTfsDeactivateGuardingReqMonitor.md). Only one DUT can be monitored at a time.

The description of [coTfsActivateHeartbeatMonitor](CAPLfunctionCoTfsActivateHeartbeatMonitor.md) contains a temporal representation that can be applied sensibly to this function.

## Parameters

- **nodeID**: Node-ID of the DUT.
- **guardTime**: Guarding time in us.
- **tolerance**: Permitted time deviation of the target device in us. It is recommended that you use an even value. The tolerated time frame within which a message is still accepted is: `x - (delta/2) <= x <= x + (delta/2)`

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsActivateGuardingReqMonitor( 0x1, 100, 20 );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)