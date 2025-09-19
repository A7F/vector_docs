[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetWakeupBahvior.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetWakeupBehavior

# linSetWakeupBehavior

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `linSetWakeupBehavior(dword restartScheduler, dword wakeupIdentifier); // form 1`
- `linSetWakeupBehavior(dword restartScheduler, dword wakeupIdentifier, dword sendShortHeader); // form 2`
- `linSetWakeupBehavior(dword restartScheduler, dword wakeupIdentifier, dword sendShortHeader, dword wakeupDelimiterLength); // form 3`

## Description

Defines the behavior after wake-up signal or an internal wake-up.

**Note**: When LIN hardware is not in sleep mode calling this function will have no effect.

## Parameters

- **restartScheduler**: Determines if index of the slot to be started with after wakeup has to be reset, i.e. it becomes 0. If it’s not reset the next slot before entering sleep mode is used. In the case no schedule tables are defined this parameter is ignored. Value range: 0..1

- **wakeupIdentifier**: LIN frame identifier to be sent additionally directly after sending a wakeup signal. If an invalid identifier is specified i.e. not in the range 0..63:
  - When schedule tables are defined no special wakeup identifier is sent.
  - When no schedule tables are defined a **SynchBreak/SynchField** pair without an identifier is sent.
  Value range: 0..0xFF

- **sendShortHeader**: Determines whether a **SynchBreak/SynchField** pair without an identifier should be sent or not, when the conditions described above hold true. That is, when
  - No valid **wakeupIdentifier** is specified
  - No schedule tables are defined
  - **sendShortHeader** is true then a **SynchBreak/SynchField** will be sent. No such "short header" will be sent otherwise.
  Value range: 0..1

- **wakeupDelimiter**: This parameter specifies the wakeup delimiter length, i.e. the time between the end of wakeup frame and the first header sent to detect a wakeup reason. Units of this parameter as well as default value depend on the hardware settings. Value range: 3..255 (ms or bit times)

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

Configure the interface to be quiet after wakeup

```plaintext
on start
{
  // do not take any action and don’t send anything automatically after the channel is
  // set to awake mode. Use these settings if you’d like to simulate a scheduler using
  // CAPL timers.
  linSetWakeupBehavior (0, 0xff, 0);
}
```

Change wake-up behavior on receiving a sleep mode event

```plaintext
on linSleepModeEvent
{
  linSetWakeupBehavior (0, 0x1, 0, 100); // don't restart scheduler, use 0x1 as wake-up identifier, start scheduling or send the wake-up identifier after 100 ms.
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
