[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetControlProperty.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » SetControlProperty

# SetControlProperty

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `void SetControlProperty(char[] panel, char[] control, char[] property, long value);` // from 1
- `void SetControlProperty(char[] panel, char[] control, char[] property, float value);` // from 2
- `void SetControlProperty(char[] panel, char[] control, char[] property, char[] value);` // from 3

## Description

Sets a property of a Panel Designer control during runtime. On the next measurement start, the property value selected in the Panel Designer will be reloaded.

The panel is accessed by its individual panel name that is entered in the Panel Designer.

It is easier to access color properties by [makeRGB](CAPLfunctionMakeRGB.md).

**Note makeRGB**

- Up to and including CANoe DE product version 12.0 SP2, the function [makeRGB](CAPLfunctionMakeRGB.md) returned the blue value in the second byte and the red value in the fourth byte. Functions that received this value as a parameter interpreted this exchange so that the color was displayed correctly.
- From CANoe DE product 12.0 SP3, the function [makeRGB](CAPLfunctionMakeRGB.md) returns the color values in the correct order. Functions that have received this value as a parameter have also been adjusted to display the correct color again.
- Existing programs only need to be adapted if you have not used the function [makeRGB](CAPLfunctionMakeRGB.md) but you have passed the color hard coded.

The following **properties** and **values** can be set:

**Note**

The **Text** property is limited to 259 characters.

- **Control:** Button
  - **Property Parameter:** Text
  - **Value Parameter:** string
- **Control:** CAPL Output
  - **Property Parameter:** Text
  - **Value Parameter:** string
- **Control:** Check Box
  - **Property Parameter:** Text
  - **Value Parameter:** string
- **Control:** Combo Box
  - **Property Parameter:** Text
  - **Value Parameter:** string
- **Control:** LCD Control
  - **Property Parameter:** DecimalPlaces
  - **Value Parameter:** Int32
  - **Property Parameter:** NumberOfDigits
  - **Value Parameter:** Int32
- **Control:** Numeric Up/Down
  - **Property Parameter:** DecimalPlaces
  - **Value Parameter:** Int32
  - **Property Parameter:** Increment
  - **Value Parameter:** decimal
- **Control:** Panel Control Button
  - **Property Parameter:** Text
  - **Value Parameter:** string
  - **Property Parameter:** Image
  - **Value Parameter:** string
- **Control:** Progress Bar
  - **Property Parameter:** OriginValue
  - **Value Parameter:** double
  - **Property Parameter:** HoldTime
  - **Value Parameter:** Int32
- **Control:** Radio Button
  - **Property Parameter:** Text
  - **Value Parameter:** string
- **Control:** Switch
  - **Property Parameter:** ButtonMode
  - **Value Parameter:** bool
- **Control:** Input/Output Box
  - **Property Parameter:** Text
  - **Value Parameter:** string
  - **Property Parameter:** DecimalPlaces
  - **Value Parameter:** Int32
- **Control:** Track Bar
  - **Property Parameter:** LargeChange
  - **Value Parameter:** double
  - **Property Parameter:** SmallChange
  - **Value Parameter:** double
  - **Property Parameter:** TickFrequency
  - **Value Parameter:** double
- **Control:** Group Box
  - **Property Parameter:** Text
  - **Value Parameter:** string
- **Control:** Static Text
  - **Property Parameter:** Text
  - **Value Parameter:** string

## Parameters

- **panel**: Panel name, restricted to 128 characters. `""` – references all loaded panels.
- **control**: Name of the panel control, restricted to 128 characters. `""` – references all elements on the panel.
- **property**: Name of the property
- **value**: Value to be set (long, float or string value)

## Return Values

—

## Example

**Example 1: Set new title for the Group Box**

```plaintext
SetControlProperty("MyPanel", "MyGroupBox", "Text", "my new text");
```

**Example 2: Select image file for Panel Control Button**

```plaintext
SetControlProperty("MyPanel", "MyPanelControlButton", "Iamge", "..\\Images\PanelControlButtonImage.png");
```

[SetControlBackColor](CAPLfunctionSetControlBackColor.md) • [SetControlForeColor](CAPLfunctionSetControlForeColor.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)