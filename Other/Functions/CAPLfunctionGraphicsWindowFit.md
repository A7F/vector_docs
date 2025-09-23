[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGraphicsWindowFit.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » graphicsWindowFit

# graphicsWindowFit

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void graphicsWindowFit(char[] windowName, byte mode);
```

## Description

Scales symbols in a CANoe DE product [Graphics Window](../../../CANoeCANalyzer/Windows/Graphics/GraphicsWindow.md).

## Parameters

- **windowName**: The name of the Graphics Window.
- **mode**:
  - mode = 1: Fit all signals
  - mode = 2: Fit all signals Y
  - mode = 3: Fit X
  - mode = 4: Fit all signals to a special line
  - mode = 5: Fit all signals to a special line Y

## Return Values

—

## Example

```plaintext
//Clear the Graphics Window to show only data from this test case
graphicsWindowClear("Graphics");
testWaitForTimeout(2000);

//Fit all signal values
graphicsWindowFit("Graphics", 1);

//Take a capture of the window and add it to the test report
TestReportAddWindowCapture("Graphics", "", "Screenshot of Graphic window");
```
