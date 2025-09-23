# SetControlColors

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SetControlColors(char[] panel, char[] control, long backcolor, long textcolor);
```

## Description

Sets the background and text color of: [certain panel controls](../../../../../Subsystems/VectorToolsEnvironment/Content/Topics/PanelDesigner/General/PanelDesignerCAPLFunctions.md).

The panel is accessed by its individual panel name that is entered in the **Panel Designer**.

## Parameters

- **panel**: Panel name, restricted to 128 characters. `""` – references all loaded panels.

- **control**: Name of the control, restricted to 128 characters. You can only activate/deactivate the control with its name. If you want to use the name of a symbol (signal or system variable) you have to ensure that the control has **no** name instead of the individual control's name.

  - The form for signals is: `"Signal:<signal name>"`.
  - The form for system variables is: `"SysVar:<name of system variable>"`.

  **Note**: Symbol assignment is not case sensitive. If you want to access all elements of a panel, the notation `""` is used.

  **Example**:
  - `"Signal:SleepInd"`
  - `"Signal:easy/MotorState/EngineSpeed"`
  - `"SysVar:SysVarTester"`

  **Note for 'CAPL Output View' Control**: When changing the background and text color only the following/future output — using [putValueToControl](CAPLfunctionPutValueToControl.md) — is colored with the new one. The existing output stays unchanged in color.

- **backcolor**: Color value (e.g. calculated by [makeRGB](CAPLfunctionMakeRGB.md)).

  **Note makeRGB**:
  - Up to and including CANoe DE product version 12.0 SP2, the function [makeRGB](CAPLfunctionMakeRGB.md) returned the blue value in the second byte and the red value in the fourth byte.
  - From CANoe DE product 12.0 SP3, the function [makeRGB](CAPLfunctionMakeRGB.md) returns the color values in the correct order.

- **textcolor**: Color value (e.g. calculated by [makeRGB](CAPLfunctionMakeRGB.md)).

## Return Values

—

## Example

```plaintext
//Set the background and text color for a specific control of a panel
SetControlColors("motor", "PedalPos", MakeRGB(255,0,0), MakeRGB(0,0,255));

//All controls of the panel are set to the same background and text color
SetControlColors("motor", "", MakeRGB(255,0,0), MakeRGB(0,0,255));

//All controls of all panels are set to the same background and text color
SetControlColors("", "", MakeRGB(255,0,0), MakeRGB(0,0,255));
```

[SetControlProperty](CAPLfunctionSetControlProperty.md) • [SetControlForeColor](CAPLfunctionSetControlForeColor.md) • [SetControlBackColor](CAPLfunctionSetControlBackColor.md) • [SetDefaultControlColors](CAPLfunctionSetDefaultControlColors.md)
