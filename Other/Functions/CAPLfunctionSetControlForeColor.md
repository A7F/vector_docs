[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetControlForeColor.md)

**CAPL Functions** » **General** » **Function Overview** » **SetControlForeColor**

# SetControlForeColor

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SetControlForeColor(char[] panel, char[] control, long color);
```

## Description

Sets the foreground color of: [certain panel controls](../../../../../Subsystems/VectorToolsEnvironment/Content/Topics/PanelDesigner/General/PanelDesignerCAPLFunctions.md). The panel is accessed by its individual panel name that is entered in the *Panel Designer*.

## Parameters

- **panel**: Panel name, restricted to 128 characters. `""` – references all loaded panels.
- **control**: Name of the control, restricted to 128 characters. You can only activate/deactivate the control with its name. If you want to use the name of a symbol (signal or system variable), ensure the control has no name instead of the individual control's name.  
  - The form for signals is: `"Signal:<signal name>"`.
  - The form for system variables is: `"SysVar:<name of system variable>"`.

  **Note**:  
  - Symbol assignment is not case sensitive.
  - If you want to access all elements of a panel, use the notation `""`.

  **Example**:  
  - `"Signal:SleepInd"`
  - `"Signal:easy/MotorState/EngineSpeed"`
  - `"SysVar:SysVarTester"` (for a system variable defined with namespace TestSysvar in the configuration)

  **Note for 'CAPL Output View' Control**: When changing the text color, only the following/future output — using [putValueToControl](CAPLfunctionPutValueToControl.md) — is colored with the new one. The existing output stays unchanged in color.

- **color**: Color value (e.g., calculated by [makeRGB](CAPLfunctionMakeRGB.md)).

  **Note makeRGB**:  
  - Up to and including CANoe DE product version 12.0 SP2, the function [makeRGB](CAPLfunctionMakeRGB.md) returned the blue value in the second byte and the red value in the fourth byte. Functions that received this value as a parameter interpreted this exchange so that the color was displayed correctly.
  - From CANoe DE product 12.0 SP3, the function [makeRGB](CAPLfunctionMakeRGB.md) returns the color values in the correct order. Functions that have received this value as a parameter have also been adjusted to display the correct color again.
  - Existing programs only need to be adapted if you have not used the function [makeRGB](CAPLfunctionMakeRGB.md) but you have passed the color hard-coded.

## Return Values

—

## Example

```plaintext
// Set the foreground color for a specific control of a panel
SetControlForeColor("motor", "PedalPos", MakeRGB(255,0,0));

// All controls of the panel are set to the same foreground color
SetControlForeColor("motor", "", MakeRGB(255,0,0));

// All controls of all panels are set to the same foreground color
SetControlForeColor("", "", MakeRGB(255,0,0));
```

[SetControlBackColor](CAPLfunctionSetControlBackColor.md) • [SetControlProperty](CAPLfunctionSetControlProperty.md) • [SetControlColors](CAPLfunctionSetControlColors.md) • [SetDefaultControlColors](CAPLfunctionSetDefaultControlColors.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
