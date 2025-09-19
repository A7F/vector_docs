[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGraphicsWindowPause.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » graphicsWindowPause

# graphicsWindowPause

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
void graphicsWindowPause(char[] windowName, byte active);
```

## Description

Pauses and resumes a CANoe DE product [Graphics Window](../../../CANoeCANalyzer/Windows/Graphics/GraphicsWindow.md).

## Parameters

- **windowName**: The name of the Graphics Window.
- **[active](../../../CANoeCANalyzer/Windows/Graphics/GraphicsDiagramPause.md)**:
  - active = 0: Pause off
  - active = 1: Pause on

## Return Values

—

## Example

```c
//Pause the Graphics Window
graphicsWindowPause("Graphics", 1);

//Fit the y axis so that all values are visible
graphicsWindowFit("Graphics", 2);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
