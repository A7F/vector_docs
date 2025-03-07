[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestStep.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestStep, TestStepPass, TestStepFail, TestStepWarning, TestStepInconclusive, TestStepErrorInTestSystem

# TestStep, TestStepPass, TestStepFail, TestStepWarning, TestStepInconclusive, TestStepErrorInTestSystem

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
The forms without parameters or with only one parameter description should only be used in combination with [TestStepBegin](CAPLfunctionTestStepBegin.md).

## Function Syntax

- `TestStep (dword LevelOfDetail, char Identifier[], char Description[], ...); // form 1`
- `TestStep (dword LevelOfDetail, char[] Identifier, long handle); // form 2`
- `TestStep (char Identifier[], char Description[], ...); // form 3`
- `TestStepPass (dword LevelOfDetail, char Identifier[], char Description[], ...); // form 4`
- `TestStepPass (dword LevelOfDetail, char[] Identifier, long handle); // form 5`
- `TestStepPass (char Identifier[], char Description[], ...); // form 6`
- `TestStepPass (char Description[]); // form 7`
- `TestStepPass (); // form 8`
- `TestStepFail (dword LevelOfDetail, char Identifier[], char Description[], ...); // form 9`
- `TestStepFail (dword LevelOfDetail, char[] Identifier, long handle); // (10)`
- `TestStepFail (char Identifier[], char Description[], ...); // form 11`
- `TestStepFail (char Description[]); // form 12`
- `TestStepFail (); // form 13`
- `TestStepWarning (dword LevelOfDetail, char Identifier[], char Description[], ...); // form 14`
- `TestStepWarning (dword LevelOfDetail, char[] Identifier, long handle); // form 15`
- `TestStepWarning (char Identifier[], char Description[], ...); // form 16`
- `TestStepWarning (char Description[]); // form 17`
- `TestStepWarning (); // form 18`
- `TestStepInconclusive (dword LevelOfDetail, char Identifier[], char Description[], ...); // form 19`
- `TestStepInconclusive (dword LevelOfDetail, char[] Identifier, long handle); // form 20`
- `TestStepInconclusive (char Identifier[], char Description[], ...); // form 21`
- `TestStepInconclusive (char Description[]); // form 22`
- `TestStepInconclusive (); // form 23`
- `TestStepErrorInTestSystem (dword LevelOfDetail, char Identifier[], char Description[], ...); // form 24`
- `TestStepErrorInTestSystem (dword LevelOfDetail, char[] Identifier, long handle); // form 25`
- `TestStepErrorInTestSystem (char Identifier[], char Description[], ...); // form 26`
- `TestStepErrorInTestSystem (char Description[]); // form 27`
- `TestStepErrorInTestSystem (); // form 28`

## Description

With these functions, test steps can be reported within a test case.

- **TestStep** reports a test step without influence on the result.
- **TestStepPass** reports a test step that was executed as expected. This is displayed accordingly in the test report.
- **TestStepFail** describes a test step that causes an error. Also this is displayed accordingly in the test report. The verdict of the test case is hereby set automatically to fail.
- **TestStepWarning** describes a test case that was executed without errors but whose result could contribute to a problem later on. This is represented appropriately in the test report.
- **TestStepInconclusive** describes a test step which cannot be clearly marked as passed or failed. Also this is displayed accordingly in the test report. The verdict of the test case is hereby set automatically to inconclusive.
- **TestStepErrorInTestSystem** describes a test step that causes an error in test system. Also this is displayed accordingly in the test report. The verdict of the test case is hereby set automatically to error in test system.

## Parameters

- **LevelOfDetail**: It is possible to identify with a number how important this test step is. In the test report, it is possible that only test steps up to a certain importance will be displayed. 0 means "very important", higher numbers indicate lower degrees of importance. Without an explicit specification, a LevelOfDetail of 0 is assumed.
- **Identifier**: E.g. a test step number) of the test step.
- **Description** of the test step: To obtain line breaks (in form of `<br />` tags) in the CANoe Test Report Viewer or in HTML test report, "\n" may be inserted at any place. The required replacement takes place during the transformation of the XML test report into an HTML file by means of an XSLT style sheet, where it can also be deactivated (see CANoe [Test:Tips & Tricks](../../../CANoeCANalyzer/Test/TestTips.md)). The description can also contain values that are read out of variables. For that the corresponding sequences like the format string of [snprintf](../../Other/Functions/CAPLfunctionSnPrintf.md) are inserted in the description. The corresponding variables are added to the parameter list. The format string has the same meaning as with the [write](../../Other/Functions/CAPLfunctionWrite.md) function and is described there.

  **Note**  
  `TestStepPass("10.2", "Output voltage ok (Uout = %d volts)", voltage);`

- **handle**: Handle to the table to be displayed within the step content, created by the function [TestInfoTable](CAPLfunctionTestInfoTable.md).

## Return Values

—

## Example

**Example**  
See example: [TestCaseTitle, TestCaseDescription, TestStep](CAPLfunctionsTFSExampleTestCaseTitleTestCaseDescriptionTestStep.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)