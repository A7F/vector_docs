[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINChangeSchedtable.md)

**CAPL Functions** » **LIN** » **linChangeSchedtable**

# linChangeSchedtable

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
long linChangeSchedTable(dword tableIndex);
long linChangeSchedTable(dword tableIndex, dword slotIndex);
long linChangeSchedTable(dword tableIndex, dword slotIndex, dword onSlotIndex);
```

## Description

This function switches from the current schedule table to another one.

By calling this function in the event procedure [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md), it is possible to specify in which schedule table the measurement should start.

**Note**

- If this function is called multiple times before the new schedule table is started, only the most recent call will have an effect. To ensure that the new table has been started, wait until the [on linSchedulerModeChange](../EventProcedures/CAPLfunctionOnLINSchedulerModeChange.md) event procedure is called.
- If the Master node is not simulated or no schedule tables are defined, then this function will have no effect.

## Parameters

- **tableIndex**: Index of the schedule table to be changed to.  
  Value range: 0..N-1, where N is a total number of defined schedule tables.

- **slotIndex**: Index of slot to be started within the new schedule table.  
  Default value: 0  
  Value range: 0..Y-1, where Y is a total number of slots in the new schedule table.

- **onSlotIndex**: Index of last slot in the current schedule table to be sent before changing to the new schedule table.  
  Default value: -2 - makes change immediately  
  Value range: -2..X-1, where X is a total number of slots in the current schedule table.  
  Value: -1 - makes change on reaching the end of current schedule table.  
  Value: -2 - makes change immediately.

## Return Values

Index of the current schedule table or -1 if no active schedule table exists and on failure.

## Example

Change to schedule table with index 1 on pressing 'c' key

```
...
on key 'c'
{
    linChangeSchedTable(1);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)