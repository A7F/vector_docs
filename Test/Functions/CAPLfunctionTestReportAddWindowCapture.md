# TestReportAddWindowCapture

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note about window captures during test preparation and completion:**

Calling `TestReportAddWindowCapture` is not supported in the MainTest function. If you want to capture windows during test preparation and completion within the MainTest function, you must implement these calls as individual test case functions that are named e.g. **preparation** and **completion** (as with XML test modules). This also lets you obtain the captured window images in their appropriate time sequence, e.g. at the beginning and end of a report.

## Function Syntax

- `TestReportAddWindowCapture(char[] window, char[] data, char[] title, char[] file); //form 1: deprecated`
- `TestReportAddWindowCapture(char[] window, char[] data, char[] title); // form 2`

## Description

[Creates a screen capture](../../../CANoeCANalyzer/Test/TestReport/TestReportWindowCapture.md) of the window and panels. Can only be used within test cases (`test case` function). The test case verdict is not affected. Errors that occur during window capture are logged in the report as **warnings**, but do not affect the test case verdict. Window capture is not allowed in [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md). Errors on creating the window capture are reported as a **warning** in the test report.

## Parameters

- **window**: Name of the window to be captured.
- **data (optional, otherwise "")**: Additional [window specific parameter](../../../CANoeCANalyzer/Test/TestReport/TestReportWindowCapture.md) (see example 2).
- **title**: Text heading that precedes the captured window image in the test report.
- **file**: Name of the file into which the captured image is to be saved. If you do not specify a name, an automatic filename is generated. Existing files with the same name will be overwritten without confirmation.

  **Note**: The parameter **file** should not be used because in combination with the function [testReportFileName](CAPLfunctionTestReportFileName.md) or with the test reporting field codes it may produce path collisions or undefined behavior. Without usage of **file** parameter, the capture files will be created and managed automatically.

## Return Values

—

## Example

**Example 1**

```c
testcase tc_1_1()
{
   TestCaseTitle("tc_1_1",  "Test Case  1.1");
   TestReportAddWindowCapture("Trace - Report", "", "Trace  before execution of test case:", "tc-1.1-trace-before");

   ...  execute Test Pattern(s) ...

   if  (TestGetVerdictLastTestCase() != 0) {
      TestReportAddWindowCapture("Trace - Report", "", "Testfall  failed. Trace am  Ende:", "tc-1.1-trace-after");
   }
}
```

**Example 2**

```c
TestReportAddWindowCapture("Graphics", "ABSdata::CarSpeed;Gear", "Screenshot of Graphic window");
```

[Test Report: Window Capture](../../../CANoeCANalyzer/Test/TestReport/TestReportWindowCapture.md)
