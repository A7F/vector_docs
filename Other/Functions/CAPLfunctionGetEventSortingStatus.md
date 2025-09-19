[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetEventSortingStatus.md)

## GetEventSortingStatus

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » GetEventSortingStatus

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

- `int GetEventSortingStatus(message msg);`
- `int GetEventSortingStatus(pg msg);`
- `int GetEventSortingStatus(gmLanMessage msg);`
- `int GetEventSortingStatus(linFrame msg);`
- `int GetEventSortingStatus(mostMessage msg);`
- `int GetEventSortingStatus(mostAmsMessage msg);`
- `int GetEventSortingStatus(mostRawMessage msg);`
- `int GetEventSortingStatus(j1587Param msg);`
- `int GetEventSortingStatus(linBaudrateEvent event);`
- `int GetEventSortingStatus(linCsError event);`
- `int GetEventSortingStatus(linDlcinfo event);`
- `int GetEventSortingStatus(linReceiveError event);`
- `int GetEventSortingStatus(linSchedulerModeChange event);`
- `int GetEventSortingStatus(linSlaveTimeout event);`
- `int GetEventSortingStatus(linSleepModeEvent event);`
- `int GetEventSortingStatus(linSyncError event);`
- `int GetEventSortingStatus(linTransmError event);`
- `int GetEventSortingStatus(linWakeupFrame event);`
- `int GetEventSortingStatus(beanError event);`
- `int GetEventSortingStatus(mostLightLockError event);`
- `int GetEventSortingStatus(FRSlot event);`
- `int GetEventSortingStatus(FRFrame msg);`
- `int GetEventSortingStatus(FrStartCycle event);`

### Description

Determines the Event Sorting state.

With active Event Sorting the return value indicates if the given event in the Simulation Setup of CANoe DE product was processed in correct time sequence.

### Parameters

- **Message event variable of type**: `"message"`, `"pg"`, `"gmLanMessage"`, `"linFrame"`, `"mostMessage"`, `"mostAmsMessage"`, `"mostRawMessage"`, `"j1587Param"`, `"linBaudrateEvent"`, `"linCsError"`, `"linDlcinfo"`, `"linReceiveError"`, `"linSchedulerModeChange"`, `"linSlaveTimeout"`, `"linSleepModeEvent"`, `"linSyncError"`, `"linTransmError"`, `"linWakeupFrame"`, `"beanError"`, `"mostLightLockError"`, `"FRSlot"`, `"FRFrame"` or `"FrStartCycle"`.

### Return Values

- **0**: Invalid state
  - The Event Sorting is inactive or it concerns a program internal event that will never be sorted (e.g. environment variable).
- **1**: sorted
  - The Event Sorting is active and the event was processed and sorted in the correct time sequence.
- **2**: unsorted
  - The Event Sorting is active but the event arrived too late or too soon so that the event was processed unsorted.

### Example

```plaintext
on message *
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on linSlaveTimeout
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on linTransmError
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on linCsError
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on linReceiveError
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on linSyncError
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on pg *
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on gmLanMessage *
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on linFrame *
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on mostMessage *
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on mostRawMessage
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on mostAMSMessage *
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on J1587Param *
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event", (double)this.msgOrigTime/100000 );
    }
}

on linBaudrateEvent
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on linDlcInfo
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on linSchedulerModeChange
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on linSleepModeEvent
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on linWakeupFrame
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on mostLightLockError
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on FRSlot *
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on FRFrame *
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}

on FRStartCycle *
{
    if ( GetEventSortingStatus(this)==2 ) {
        Write("Unsorted Event at time %.6f", (double)this.time/100000 );
    }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
