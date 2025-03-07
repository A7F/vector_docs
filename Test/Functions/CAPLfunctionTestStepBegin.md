[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestStepBegin.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestStepBegin

# TestStepBegin

Valid for: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**

`TestStepBegin` must be concluded with a second [TestStepPass, TestStepFail or TestStepWarning](CAPLfunctionTestStep.md). Here the variants of these [TestStep](CAPLfunctionTestStep.md) commands must be used without parameters or with one parameter. Only if this second `TestStep` command is executed a test step is noted in the report. If this second TestStep command is forgotten, then the test step is concluded automatically as soon as another report command arises (this also applies for the TestStep variants with two and three parameters).

Between `TestStepBegin` and the closing [TestStepPass/TestStepFail/TestStepWarning](CAPLfunctionTestStep.md) no kind of "wait" command (`TestWaitFor...`) must be used. This is due to possible report output during wait commands (e.g. resume reasons, constraint/condition violation).

The variant `TestStepBegin` plus [TestStepPass/TestStepFail/TestStepWarning](CAPLfunctionTestStep.md) for the entry of test steps into the report offers the opportunity to structure the code more clearly without additional comments. At the beginning of the program piece that implements a test step (typically a short piece of code with a condition to determine the test step result), it is now possible to specify with `TestStepBegin` the importance, the test step identification, and the description of what is done in this test step. With this `TestStepBegin` line it is possible to avoid a corresponding initial comment before the test step implementation. As soon as the result has been determined within the test step implementation, it is completed with [TestStepPass, TestStepFail or TestStepWarning](CAPLfunctionTestStep.md). At this point the test step can also be taken over into the report. Potentially in this second TestStep command, the descriptive test is also completed, usually with a precise description of the problem that occurred.

## Function Syntax

`TestStepBegin (dword Importance, char Identifier[], char Description[]);`

`TestStepBegin (char Identifier[], char Description[]);`

## Description

With these functions, test steps can be logged within a test case. Such a test step is introduced with `TestStepBegin`, which is then completed with [TestStepPass, TestStepFail or TestStepWarning](CAPLfunctionTestStep.md). A test step is noted in the test report only with this conclusion.

## Parameters

- **Importance**: It is possible to identify with a number how important this test step is. In the test report, it is possible that only test steps up to a certain importance will be displayed. 0 means "very important", higher numbers indicate lower degrees of importance. Without an explicit specification, the importance 0 is assumed.

- **Identifier** (e.g. a test step number) of the test step

- **Description** of the test step: A possibly-specified descriptive text in the concluding [TestStepPass, TestStepFail or TestStepWarning](CAPLfunctionTestStep.md) is added to this descriptive text. To obtain line breaks (in form of `<br />` tags) in the test report, "\n" may be inserted at any place. The required replacement takes place during the transformation of the XML test report into an HTML file by means of an XSLT style sheet, where it can also be deactivated.

## Return Values

—

## Example

```plaintext
TestStepBegin (0, "3.1", "Receipt of response message");
if (result == 1)
    TestStepPass ();
else
    TestStepFail ("failed because of Timeout");
```

[TestStep, TestStepPass, TestStepFail, TestStepWarning](CAPLfunctionTestStep.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)