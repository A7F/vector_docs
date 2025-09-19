[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINRunSchedTableNtimes.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linRunSchedTableNtimes

# linRunSchedTableNtimes

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long linRunSchedTableNtimes (dword tableIndex, dword numberOfRepetitions, dword onSlotIndex, dword returnToTableIndex);
```

## Description

Switches from the current schedule table to another one, runs the table **n** times and returns to the initial table or to a different table.

**Note**: This function only works with LIN core network interfaces.

## Parameters

- **tableIndex**: Index of the schedule table to be changed to.  
  Value range: 0..n-1, where **n** is a total number of defined schedule tables.

- **numberOfRepetitons**: Number of repetitions of the schedule table.

- **onSlotIndex**: Index of last slot in the current schedule table to be sent before changing to the new schedule table.  
  Default value: -1, make change on reaching the end of current schedule table.  
  Value range: -1..x-1, where **x** is a total number of slots in the current schedule table.

- **returnToTableIndex**: Default value: -1, return to previous table.  
  Value range: 0..n-1, where **n** is a total number of defined schedule tables.

## Return Values

Index of the current schedule table or -1 if no active schedule table exists and on failure.

## Example

```plaintext
// on pressing key ‘c’ change to schedule table with index 1, run it 2 times and return to the previous table
...
on key 'c'
{
  linRunSchedTableNTimes (1, 2, -2, -1);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
