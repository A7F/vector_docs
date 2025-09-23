[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGraphicsWindowClear.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » graphicsWindowClear

# graphicsWindowClear

**Valid for**: [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
void graphicsWindowClear (char[] windowName);
```

## Description

Temporarily deletes the contents of the CANoe DE product [Graphics Window](../../../CANoeCANalyzer/Windows/Graphics/GraphicsWindow.md). E.g. with [TestReportAddWindowCapture](../../Test/Functions/CAPLfunctionTestReportAddWindowCapture.md) a screenshot is created that contains only the data of a certain period of time.

## Parameters

- **windowName**: The name of the Graphics Window.

## Return Values

—

## Example

```c
//Clear the Graphics Window to show only data from this test case
graphicsWindowClear("Graphics");
testWaitForTimeout(2000);

//Fit all signal values
graphicsWindowFit("Graphics", 1);

//Take a capture of the window and add it to the test report
TestReportAddWindowCapture("Graphics", "", "Screenshot of Graphic window");
```
