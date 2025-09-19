[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestCaseTitle.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestCaseTitle

# TestCaseTitle

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**

- The title must not contain parenthesis.
- The parameter **Identifier** is only supported for test modules. It is ignored for test units as test case IDs are generated in **vTESTstudio**.

## Function Syntax

TestCaseTitle (char identifier[], char title[]);

## Description

The title of a test case is acquired automatically from the test case name in the CAPL program. It can also be set explicitly together with a test case identifier with the help of this function. The function may only be called within a test case and relates then to the respective test case.

## Parameters

- **title**: Title of the test case.
- **identifier**: E.g. a test case number of the test case.

## Return Values

—

## Example

**Example 1**

```plaintext
testcase CheckLockingOnCrash ()
{
   TestCaseTitle("TC 1.0", "Check unlock of central locking system on crash");
   TestCaseDescription("This test case simulates a crash during drive. The central locking system has to be unlocked on crash!");
   // Initialization of signals
   $CrashDetected = 0;
   $LockState = Locked;
   TestWaitForTimeout(200);

   TestCaseComment("Initialization of system completed.");
   ...
}
```

**Example 2**

See example: [TestCaseTitle, TestCaseDescription, TestStep](CAPLfunctionsTFSExampleTestCaseTitleTestCaseDescriptionTestStep.md)

[TestCaseDescription](CAPLfunctionTestCaseDescription.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
