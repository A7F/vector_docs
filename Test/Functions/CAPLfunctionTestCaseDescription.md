# TestCaseDescription

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`TestCaseDescription (char description[]);`

## Description

With this function, a description test for a test case can be written into the report. The function can be called several times in a row, the transmitted texts are then added to one another without additional separation. The function may only be called within a test case and relates then to the respective test case.

To obtain line breaks (in form of `<br /\>` tags) in the test report, "\n" may be inserted at any place.

## Parameters

Description test for the test case.

## Return Values

—

## Example

**Example 1**

```c
// add description with line break to report
TestCaseDescription("In this test case\nthe occurrence of Error Frames is tested.");
```

**Example 2**

See example: [TestCaseTitle, TestCaseDescription, TestStep](CAPLfunctionsTFSExampleTestCaseTitleTestCaseDescriptionTestStep.md)

```c
testcase CheckLockingOnCrash ()
{
   TestCaseTitle("TC 1.0", "Check unlock of central locking system on crash");
   TestCaseDescription("This test case simulates a crash during drive. The central locking system has to be unlocked on crash!");
   // Initialization of signals
   $CrashDetected = 0;
   $LockState = Locked;
   TestWaitForTimeout(200);

   TestCaseComment("Initialization of system completed");
   ...
}
```

[TestCaseTitle](CAPLfunctionTestCaseTitle.md)
