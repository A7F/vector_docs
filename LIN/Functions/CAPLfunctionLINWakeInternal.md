[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINWakeInternal.md)

# linWakeupInternal

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linWakeupInternal

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long linWakeupInternal();
```

## Description

Wakes up the LIN bus without sending any wakeup signals.

**Note**

- When called during wakeup mode this function has no effect.
- This function can be useful before issuing a go-to-sleep-command in order to ensure wakeup mode.

## Parameters

—

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
