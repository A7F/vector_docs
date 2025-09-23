[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionsTFSExampleTestCaseTitleTestCaseDescriptionTestStep.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » Example: TestCaseTitle, TestCaseDescription, TestStep

# Example: TestCaseTitle, TestCaseDescription, TestStep

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Color usage

- statements
- keywords
- comments
- test functions

```plaintext
testcaseConfigure_Testmode()
{
    ...
    // set test case identification to "TC 3.12" and change test case title from
    // "Configure_Testmode" to "Test Mode Configuration"
    TestCaseTitle("TC 3.12", "Test Mode Configuration");
    // add a description text to test case
    TestCaseDescription("Test case is used to check the ability of the SUT to switch ");
    TestCaseDescription("into the build-in diagnostic and test mode. The test case does ");
    TestCaseDescription("not change test settings within the device. ");
    ...
    TestStep("1.0", "Communication prepared"); // create neutral entry in report file
    ...
    TestStepPass("2.0", "Request sent to the SUT, sig = 1"); // reporting of passed action
    ...
    switch(lRet) {
        case 0: // timeout, reporting of failed action
            TestStepFail("3.1", "WaitForResponse: Expected message did not occur. Timeout.");
            break;
        case 1: // ok, reporting of passed action
            TestStepPass("3.0", "WaitForResponse: Received message ok.");
            break;
        default: // unknown error, test case fails
            TestStepFail("3.2", "WaitForResponse: Unknown error occurred.");
            break;
    }
    ...
}
```
