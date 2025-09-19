[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetClockControlTime.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » SetClockControlTime

# SetClockControlTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```cpp
void SetClockControlTime(char[] panel, char[] control, int hours, int minutes, int seconds); // form 1
void SetClockControlTime(char[] panel, char[] control, int time); // form 2
```

## Description

Sets the time of the Panel Designer Clock Control. The panel is accessed by its individual panel name that is entered in the Panel Designer.

## Parameters

- **panel**: Panel name, restricted to 128 characters. "" – references all loaded panels. If you open a panel the first time, the panel is loaded. If you close the panel, it remains loaded.
  
- **control**: Name of the control, restricted to 128 characters. You can only access the control by its name. In the property dialog of the control, its name is assigned/displayed. If you want to use the name of a symbol (signal or system variable), you have to ensure that the control has no name instead of the individual control's name. The name of the system variable or signal could be specified as follows:
  - The form for signals is: "Signal:`<signal name>`".
  - The form for system variables is: "SysVar:`<name of system variable>`". The namespace must not be used.

  **Note**:
  - Symbol assignment is not case sensitive.
  - If you want to access all elements of a panel, the notation "" is used.

  **Example**:
  - "Signal:SleepInd"
  - "Signal:easy/MotorState/EngineSpeed"
  - "SysVar:SysVarTester" (for a system variable defined with namespace TestSysvar in the configuration)

- **hours**: Defines the hours of the time to be displayed in the clock control.

- **minutes**: Defines the minutes of the time to be displayed in the clock control.

- **seconds**: Defines the seconds of the time to be displayed in the clock control.

- **time**: Defines the time in seconds to be displayed in the clock control. The corresponding hours, minutes, and seconds are calculated during runtime.

## Return Values

—

## Example

```cpp
// Set the time in hours, minutes, seconds. It will be displayed '10:20:30'.
on key 'a'
{
    SetClockControlTime("ClockControl1", "ClockCAPL", 10, 20, 30);
}

// Set the time in seconds. It will be displayed '01:00:00'.
on key 'b'
{
    SetClockControlTime("ClockControl1", "ClockCAPL", 3600);
}
```

[SetControlProperty](CAPLfunctionSetControlProperty.md) • [SetControlForeColor](CAPLfunctionSetControlForeColor.md) • [SetControlBackColor](CAPLfunctionSetControlBackColor.md) • [SetDefaultControlColors](CAPLfunctionSetDefaultControlColors.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
