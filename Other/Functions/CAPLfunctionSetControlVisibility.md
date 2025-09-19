[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetControlVisibility.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » SetControlVisibility

# SetControlVisibility

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SetControlVisibility(char[] panel, char[] control, long visible);
```

## Description

Sets the visibility of all panel controls. The panel is accessed by its individual panel name that is entered in the Panel Designer.

## Parameters

- **panel**: Panel name, restricted to 128 characters. "" – references all loaded panels. If you open a panel the first time, the panel is loaded. If you close the panel, it remains loaded.

- **control**: Name of the control, restricted to 128 characters. You can only activate/deactivate the control with its name. In the property dialog of the control, its name is assigned/displayed. If you want to use the name of a symbol (signal or system variable), you have to ensure that the control has no name instead of the individual control's name. The name of the system variable or signal could be specified as follows.

  - The form for signals is: "Signal:`<signal name>`".
  - The form for system variables is: "SysVar:`<name of system variable>`". The namespace must not be used.

  **Note**: If you want to access all elements of a panel, the notation "" is used, see example below.

  **Example**: 
  - "Signal:SleepInd"
  - "SysVar:SVInteger"

- **visible**: Sets if the panel element should be visible or not.
  - visible = 1 => Panel element is visible
  - visible = 0 => Panel element is not visible

## Return Values

—

## Example

```plaintext
// Set the visibility for a specific control of a panel
SetControlVisibility("motor", "PedalPos", 1);

// All controls of the panel are set to not visible
SetControlVisibility("motor", "", 0);

// All controls of all panels are set to visible
SetControlVisibility("", "", 1);
```

[SetControlBackColor](CAPLfunctionSetControlBackColor.md) • [SetControlProperty](CAPLfunctionSetControlProperty.md) • [SetControlColors](CAPLfunctionSetControlColors.md) • [SetDefaultControlColors](CAPLfunctionSetDefaultControlColors.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)