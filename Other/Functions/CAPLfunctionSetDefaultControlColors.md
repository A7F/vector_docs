# SetDefaultControlColors

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SetDefaultControlColors(char[] panel, char[] control);
```

## Description

Sets back the background and text color as defined in the Panel Designer: [certain panel controls](../../../../../Subsystems/VectorToolsEnvironment/Content/Topics/PanelDesigner/General/PanelDesignerCAPLFunctions.md).

The panel is accessed by its individual panel name that is entered in the Panel Designer.

## Parameters

- **panel**: Panel name, restricted to 128 characters. `""` – references all loaded panels. If you open a panel the first time, the panel is loaded. If you close the panel, it remains loaded.
- **control**: Name of the control, restricted to 128 characters. You can only activate/deactivate the control with its name. In the property dialog of the control, its name is assigned/displayed.

  If you want to use the name of a symbol (signal or system variable), ensure the control has no name instead of the individual control's name. The name of the system variable or signal could be specified as follows:

  - The form for signals is: `"Signal:<signal name>"`.
  - The form for system variables is: `"SysVar:<name of system variable>"`. The namespace must not be used.

  **Note**: Symbol assignment is not case sensitive. If you want to access all elements of a panel, the notation `""` is used.

  **Example**:
  - `"Signal:SleepInd"`
  - `"Signal:easy/MotorState/EngineSpeed"`
  - `"SysVar:SysVarTester"` (for a system variable defined with namespace TestSysvar in the configuration)

  **Note for 'CAPLOutputView' Control**: When changing the background and text color, only the following/future output — using [putValueToControl](CAPLfunctionPutValueToControl.md) — is colored with the new one. The existing output stays unchanged in color.

## Return Values

—

## Example

```plaintext
// Set the default background and text color for a specific control of a panel.
SetDefaultControlColors("motor", "PedalPos");

// All controls of the panel are set to the default background and text color as defined in the Panel Designer.
SetDefaultControlColors("motor", "");

// All controls of all panels are set to the default background and text color as defined in the Panel Designer.
SetDefaultControlColors("", "");
```

[SetControlProperty](CAPLfunctionSetControlProperty.md) • [SetControlForeColor](CAPLfunctionSetControlForeColor.md) • [SetControlBackColor](CAPLfunctionSetControlBackColor.md) • [SetControlColors](CAPLfunctionSetControlColors.md)
