# coTfsCbGetSettings (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsCbGetSettings( dword type, dword nodeId, dword cycleTime[1], dword tolerance[1] );
```

## Description

This function gets the set parameter of an active monitor.

## Parameters

- **type**
  - 0 - Heartbeat message
  - 1 - Sync message
  - 2 - Sync PDO message
  - 3 - Guarding RTR message for request

- **nodeId**
  - Monitored node-ID for request.

- **cycleTime[]**
  - Set cycle time.

- **tolerance[]**
  - Set tolerance.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
const kMonitorTypeHeartbeat   = 0;
const kMonitorTypeSyncMsg    = 1;
const kMonitorTypeSyncPdoMsg   = 2;
const kMonitorTypeGuardingRtrMsg = 3;
dword cycleTime[1];
dword tolerance[1];

/* assume the selected monitor is active */
/* get settings of the active monitor */
if (coTfsCbGetSettings(kMonitorTypeHeartbeat, 112, cycleTime, tolerance) != 1)
{
  ; /* failure, monitor not active?, incorrect nodeId? */
} /* if */
else
{
  write ("tolerance = %d ms, cycleTime = %d ms", tolerance[0], cycleTime[0]);
} /* else */
```
