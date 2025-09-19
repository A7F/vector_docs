[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionClockControlStop.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » ClockControlStop

# ClockControlStop

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void ClockControlStop(char[] panel, char[] control);
```

## Description

Stops the Clock Control designed as stop watch with the *Panel Designer* (setting **Mode = StopWatch**).

The displayed time stays unchanged unless the user [starts](CAPLfunctionClockControlStart.md) the stop watch again or [resets](CAPLfunctionClockControlReset.md) it.

If the stop watch is started again without resetting it, the start time is the current displayed time (not zero).

The panel is accessed by its individual panel name that is entered in the *Panel Designer*.

## Parameters

- **panel**: Panel name, restricted to 128 characters. "" – references all loaded panels. If you open a panel the first time, the panel is loaded. If you close the panel, it remains loaded.
- **control**: Name of the control, restricted to 128 characters. You can only access the control by its name. In the property dialog of the control it's name is assigned/displayed.

  If you want to use the name of a symbol (signal or system variable) you have to ensure that the control has **no** name instead of the individual control's name. The name of the system variable or signal could be specified as following.

  The form for signals is: "Signal:`<signal name>`". The form for system variables is: "SysVar:`<name of system variable>`". The namespace must not be used.

  **Note:**
  - Symbol assignment is not case sensitive.
  - If you want to access all elements of a panel the notation "" is used, see example below.

  **Example:**
  - "Signal:SleepInd"
  - "Signal:easy/MotorState/EngineSpeed"
  - "SysVar:SysVarTester" (for a system variable defined with namespace TestSysvar in the configuration)

## Return Values

—

## Example

```plaintext
// Stop the clock control designed as stop watch.
on key 'a'
{
    ClockControlStop("ClockControl", "StoppWatch");
}
```

[ClockControlStart](CAPLfunctionClockControlStart.md) • [ClockControlReset](CAPLfunctionClockControlReset.md) • [SetClockControlTime](CAPLfunctionSetClockControlTime.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
