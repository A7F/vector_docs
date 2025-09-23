[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTSystemLock.md)

## OnMostSystemLock

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostSystemLock

### Function Syntax

`OnMostSystemLock(long oldstate, long newstate);`

### Description

This event procedure is called each time the state of the System-Lock flag changes.

Within this event procedure the functions [mostEventChannel, mostEventTime and mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

### Parameters

- **oldstate**: Old state of the System Lock Flag.
- **newstate**: New state of the System Lock Flag.

### Return Values

- **1**: System Lock Flag set.
- **0**: System Lock Flag not set.

### Example

—

[mostSetSystemLockFlagUsage](../Functions/CAPLfunctionMOSTSetGetSystemLockFlagUsage.md)
