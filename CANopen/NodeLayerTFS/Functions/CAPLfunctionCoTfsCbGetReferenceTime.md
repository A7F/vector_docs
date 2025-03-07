[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsCbGetReferenceTime.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsCbGetReferenceTime

# coTfsCbGetReferenceTime (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsCbGetReferenceTime( dword type, dword nodeId, dword refTime[1], dword minTime[1], dword minOccTime[1], dword maxTime[1], dword maxOccTime[1], dword averageTime[1] );
```

## Description

This function gets the maximum, minimum, and average value of an active monitor.

## Parameters

- **type**
  - 0 - Heartbeat message
  - 1 - Sync message
  - 2 - Sync PDO message
  - 3 - Guarding RTR message for request

- **nodeId**
  - Monitored node-ID for request.

- **refTime[]**
  - Reference time of the last executed callback [ms].

- **minOccTime[]**
  - Minimum time stamp of occurrence [ms].

- **maxTime[]**
  - Maximum time difference [ms].

- **maxOccTime[]**
  - Maximum time stamp of occurrence [ms].

- **averageTime[]**
  - Average time of all callbacks.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
const kMonitorTypeHeartbeat   = 0;
const kMonitorTypeSyncMsg    = 1;
const kMonitorTypeSyncPdoMsg   = 2;
const kMonitorTypeGuardingRtrMsg = 3;
dword refTime[1];
dword minTime[1];
dword minOccTime[1];
dword maxTime[1];
dword maxOccTime[1];
dword averageTime[1];

/* assume the selected monitor is active */
/* get reference time of the active monitor */
if (coTfsCbGetReferenceTime(kMonitorTypeHeartbeat, 112, refTime, minTime, minOccTime, maxTime, maxOccTime, averageTime) != 1)
{
  ; /* failure, monitor not active?, incorrect nodeId? */
} /* if */
else
{
  write ("last message monitored = %d ms, average time = %d ms", refTime[0], averageTime[0]);
  write ("minimum time = %d ms, time stamp of that event = %d ms", minTime[0], minOccTime[0]);
  write ("maximum time = %d ms, time stamp of that event = %d ms", maxTime[0], maxOccTime[0]);
} /* else */
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)