# coTfsMonitorSetLssTimeout (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsMonitorSetLssTimeout( dword lssTimeoutInMs );
```

## Description

This function sets the LSS timeout for the passive communication monitor.

You can start the monitoring with [coTfsMonitorActivate](CAPLfunctionCoTfsMonitorActivate.md) and stop it with [coTfsMonitorDeactivate](CAPLfunctionCoTfsMonitorDeactivate.md).

To include node-IDs or ranges of node-IDs for monitoring you can use the functions [coTfsMonitorIncludeNodeId](CAPLfunctionCoTfsMonitorIncludeNodeId.md) and [coTfsMonitorIncludeNodeIdRange](CAPLfunctionCoTfsMonitorIncludeNodeIdRange.md). For exclusion you can use [coTfsMonitorExcludeNodeId](CAPLfunctionCoTfsMonitorExcludeNodeId.md) and [coTfsMonitorExcludeNodeIdRange](CAPLfunctionCoTfsMonitorExcludeNodeIdRange.md).

## Parameters

- **lssTimeoutInMs**: Timeout in ms, default value: 200 ms.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
// configure node-IDs for monitoring: monitor nodes 1..14, 21..24, 26..64 and 127
coTfsMonitorIncludeNodeIdRange( 1, 64);
coTfsMonitorExcludeNodeIdRange( 15, 20);
coTfsMonitorExcludeNodeId   ( 25);
coTfsMonitorIncludeNodeId   (127);

coTfsMonitorSetLssTimeout( 100 ); // set LSS timeout to 100 ms
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
