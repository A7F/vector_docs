[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionClockControlReset.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » ClockControlReset

# ClockControlReset

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void ClockControlReset(char[] panel, char[] control);
```

## Description

Resets the Clock Control designed as stop watch with the *Panel Designer* (setting **Mode = StopWatch**).

The displayed time is reset to **00:00:00** or **00:00** depending on the *Panel Designer* setting **Display Seconds**.

**Note**: The stop watch cannot be reset when it is already running.

The panel is accessed by its individual panel name that is entered in the *Panel Designer*.

## Parameters

- **panel**: Panel name, restricted to 128 characters. `""` – references all loaded panels.

- **control**: Name of the control, restricted to 128 characters. You can only access the control by its name. If you want to use the name of a symbol (signal or system variable) you have to ensure that the control has **no** name instead of the individual control's name.

  - The form for signals is: "Signal:`<signal name>`".
  - The form for system variables is: "SysVar:`<name of system variable>`". The namespace must not be used.

  **Note**:
  - Symbol assignment is not case sensitive.
  - If you want to access all elements of a panel the notation `""` is used.

  **Example**:
  - "Signal:SleepInd"
  - "Signal:easy/MotorState/EngineSpeed"
  - "SysVar:SysVarTester" (for a system variable defined with namespace TestSysvar in the configuration)

## Return Values

—

## Example

```plaintext
// Reset the clock control designed as stop watch.
on key 'a'
{
    ClockControlReset("ClockControl", "StoppWatch");
}
```

[ClockControlStart](CAPLfunctionClockControlStart.md) • [ClockControlStop](CAPLfunctionClockControlStop.md) • [SetClockControlTime](CAPLfunctionSetClockControlTime.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)