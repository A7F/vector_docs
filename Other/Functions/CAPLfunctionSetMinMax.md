[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetMinMax.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » SetMinMax

# SetMinMax

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
bool SetMinMax(char[] panel, char[] control, float min, float max);
```

## Description

Sets the minimum and maximum value of: [certain panel controls](../../../../../Subsystems/VectorToolsEnvironment/Content/Topics/PanelDesigner/General/PanelDesignerCAPLFunctions.md)

The panel is accessed by its individual panel name that is entered in the *Panel Designer*.

## Parameters

- **panel**: Panel name, restricted to 128 characters. "" – references all loaded panels.
- **control**: Name of the control, restricted to 128 characters. "" – references all elements on the panel.
- **minimum**: Minimum value to be set.
- **maximum**: Maximum value to be set.

## Return Values

If the values were set, the return value is 1, else 0.

## Example

```plaintext
SetMinMax("Measurements", "MyLevelMeter", 50, 100);
```

[SetControlBackColor](CAPLfunctionSetControlBackColor.md) • [SetControlProperty](CAPLfunctionSetControlProperty.md) • [SetControlColors](CAPLfunctionSetControlColors.md) • [SetDefaultControlColors](CAPLfunctionSetDefaultControlColors.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
