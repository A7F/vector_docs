[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionEnableControl.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » enableControl

# enableControl

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void enableControl(char panel[], char control[], long enable);
```

## Description

Selective activation and deactivation of: [certain panel controls](../../../../../Subsystems/VectorToolsEnvironment/Content/Topics/PanelDesigner/General/PanelDesignerCAPLFunctions.md)

If a control and display element is configured as a simple display, this command will have no effect on the element in question. The turned on or turned off state of an element remains intact at the start/end of the measurement. Because of this, a defined state should be created for the beginning of the measurement for the elements involved (for example in the CAPL program under System->Start).

## Parameters

- **panel**: Name of the panel, restricted to 128 characters. If an empty string is transferred, the action will affect all loaded panels.

- **control**: Name of the control, restricted to 128 characters. You can only activate/deactivate the control with its name. If you want to use the name of a symbol (signal or system variable) you have to ensure that the control has no name instead of the individual control's name. The form for signals is: "Signal:<signal name>". The form for system variables is: "SysVar:<name of system variable>". The namespace must not be used.

  **Note:**
  - Symbol assignment is not case sensitive.
  - If you want to access all elements of a panel the notation "" is used, see example below.
  - When a **GroupBox** or **TabControl** is activated/deactivated, all controls in the GroupBox or TabControl are also activated/deactivated. See example below.

  **Example:**
  - "Signal:SleepInd"
  - "Signal:easy/MotorState/EngineSpeed"
  - "SysVar:SysVarTester" (for a system variable defined with namespace TestSysvar in the configuration)

- **enable**:
  - `0`: turn off (disable)
  - `1`: turn on (enable)

## Return Values

—

## Example

```plaintext
on key 'a'
{
    // enables a specific control of the "motor" panel
    enableControl("motor", "PedalPos", 1);

    // enables all controls of the panel
    enableControl("motor", "", 1);

    // disables the GroupBox and all controls in the GroupBox:
    enableControl("Controlpanel", "LightGroupBox", 0);

    // disables the TabControl and all controls on the TabControl:
    enableControl("DisplayPanel", "TabControl1", 0);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)