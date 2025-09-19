[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestCaseComment.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestCaseComment

# TestCaseComment

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `TestCaseComment (char aComment[]);`
- `TestCaseComment (char aComment[], message aMsg);`
- `TestCaseComment (char aComment[], mostMessage aMsg);`
- `TestCaseComment (char aComment[], mostAmsMessage aMsg);`
- `TestCaseComment (char aComment[], mostRawMessage aMsg);`
- `TestCaseComment (char aComment[], linFrame aMsg);`
- `TestCaseComment (char aComment[], char aRawString[]);`
- `TestCaseComment (char aComment[], gmLanMsg aMsg);`

## Description

With this function within a test case a commentary can be taken over into the report. This comment can relate to a message that can also be output in the report. The verdict of the test case is not influenced.

## Parameters

- **aComment**: Commentary to be taken over into the report.
- **aMsg**: CAN-, GMLAN-, LIN-, MOST-, MOST-AMS- or MOST system message to be taken over into the report.
- **aRawString**: Here you may enter any ASCII characters. They will be added to the comment in the following way: `<Hex value of the given character>(<ASCII display of the given character>)`. In ASCII display special characters will be replaced by `.`.

## Return Values

—

## Example

```plaintext
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

[TestCaseFail](CAPLfunctionTestCaseFail.md) • [TestStep](CAPLfunctionTestStep.md) • [TestStepFail](CAPLfunctionTestStep.md) • [TestStepPass](CAPLfunctionTestStep.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
