[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestCaseFail.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestCaseFail

# TestCaseFail

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
TestCaseFail ();
```

## Description

You can set the verdict of the current test case to fail. This function can only be used within a test case. It is not possible to set the verdict of this test case back to pass.

**Note**  
This function does not report any reason for the failure of the test case nor the point during test case execution where it was called. It is recommended to use [TestStepFail](CAPLfunctionTestStep.md) instead which reports a text for the reason as a step in the test execution and automatically sets the verdict of the test case to fail.

## Parameters

—

## Return Values

—

## Example

```c
// checks if the value of the signal is in the given range
testcase CheckSignalValue()
{
   long result;
   result = checkSignalInRange(Node_SUT::Velocity, 60, 100);
   if (result != 1)
      TestCaseFail();
}
```

[TestStepFail](CAPLfunctionTestStep.md) • [TestGetVerdictLastTestCase](CAPLfunctionTestGetVerdictLastTestCase.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)