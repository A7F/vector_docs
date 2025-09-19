[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionClockControlStart.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » ClockControlStart

# ClockControlStart

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void ClockControlStart(char[] panel, char[] control);
```

## Description

Starts the Clock Control designed as stop watch in the *Panel Designer* (setting **Mode = StopWatch**).

The stop watch starts with **00:00:00** or **00:00** depending on the *Panel Designer* setting **Display Seconds**. The start time cannot be changed.

The stop watch is updated every second.

**Note**: The stop watch cannot be started when it is already running.

The panel is accessed by its individual panel name that is entered in the *Panel Designer*.

## Parameters

- **panel**: Panel name, restricted to 128 characters. `""` – references all loaded panels.

- **control**: Name of the control, restricted to 128 characters. You can only access the control by its name. If you want to use the name of a symbol (signal or system variable), ensure the control has **no** name instead of the individual control's name.

  - The form for signals is: `"Signal:<signal name>"`.
  - The form for system variables is: `"SysVar:<name of system variable>"`. The namespace must not be used.

  **Note**:
  - Symbol assignment is not case sensitive.
  - If you want to access all elements of a panel, the notation `""` is used.

  **Example**:
  - `"Signal:SleepInd"`
  - `"Signal:easy/MotorState/EngineSpeed"`
  - `"SysVar:SysVarTester"` (for a system variable defined with namespace TestSysvar in the configuration)

## Return Values

—

## Example

```plaintext
// Start the clock control designed as stop watch.
on key 'a'
{
    ClockControlStart("ClockControl", "StoppWatch");
}
```

[ClockControlStop](CAPLfunctionClockControlStop.md) • [ClockControlReset](CAPLfunctionClockControlReset.md) • [SetClockControlTime](CAPLfunctionSetClockControlTime.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
