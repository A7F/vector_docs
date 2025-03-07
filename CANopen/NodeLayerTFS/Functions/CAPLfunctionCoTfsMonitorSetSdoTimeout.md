[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsMonitorSetSdoTimeout.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsMonitorSetSdoTimeout

# coTfsMonitorSetSdoTimeout (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsMonitorSetSdoTimeout( dword sdoTimeoutInMs );
```

## Description

This function sets the SDO timeout for the passive communication monitor.

You can start the monitoring with [coTfsMonitorActivate](CAPLfunctionCoTfsMonitorActivate.md) and stop it with [coTfsMonitorDeactivate](CAPLfunctionCoTfsMonitorDeactivate.md).

To include node-IDs or ranges of node-IDs for monitoring you can use the functions [coTfsMonitorIncludeNodeId](CAPLfunctionCoTfsMonitorIncludeNodeId.md) and [coTfsMonitorIncludeNodeIdRange](CAPLfunctionCoTfsMonitorIncludeNodeIdRange.md). For exclusion you can use [coTfsMonitorExcludeNodeId](CAPLfunctionCoTfsMonitorExcludeNodeId.md) and [coTfsMonitorExcludeNodeIdRange](CAPLfunctionCoTfsMonitorExcludeNodeIdRange.md).

## Parameters

- **sdoTimeoutInMs**: Timeout in ms, default value: 200 ms.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
// configure node-IDs for monitoring: monitor nodes 1..14, 21..24, 26..64 and 127
coTfsMonitorIncludeNodeIdRange( 1, 64);
coTfsMonitorExcludeNodeIdRange( 15, 20);
coTfsMonitorExcludeNodeId   ( 25);
coTfsMonitorIncludeNodeId   (127);

coTfsMonitorSetSdoTimeout( 100 ); // set SDO timeout to 100 ms
coTfsMonitorSetNmtTimeout( 2000 ); // set NMT timeout for boot-up message to 2 s

coTfsMonitorActivate();      // activate monitoring
TestWaitForTimeout(30000);     // monitor CANopen traffic for 60 seconds ...
if (coTfsMonitorDeactivate() != 1) { // deactivate monitoring and add results to report, check for errors
  TestStepFail("Monitoring", "At least one monitored response was not received in time");
}
else {
  TestStepPass("Monitoring", "All monitored responses were received in time");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)