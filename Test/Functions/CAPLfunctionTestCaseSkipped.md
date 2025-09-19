[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestCaseSkipped.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestCaseSkipped

# TestCaseSkipped

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
The parameter **Identifier** is only supported for test modules. It is ignored for test units as test case IDs are generated in vTESTstudio.

## Function Syntax

`TestCaseSkipped(char[] ident, char[] title);`

## Description

This function can be used to mark a test case as unexecuted. This will then appear as a "skipped" test case in the Test Report.  
The verdict of the test module is not affected. This function may only be called in the context of the MainTest function.

## Parameters

- **ident**: Identifier of the test case, e.g. number.
- **title**: Title of the test case.

## Return Values

—

## Example

**Example**  
test case "tc3" is only executed under certain conditions

```plaintext
MainTest
{
   tc1();
   tc2();
   if(condition)
   {
      tc3();
   }
   else
   {
      TestCaseSkipped("TC3", "Example");
   }
   tc4();
}
```

[TestCaseComment](CAPLfunctionTestCaseComment.md) • [TestCaseDescription](CAPLfunctionTestCaseDescription.md) • [TestCaseFail](CAPLfunctionTestCaseFail.md) • [TestCaseTitle](CAPLfunctionTestCaseTitle.md) • [TestStep](CAPLfunctionTestStep.md) • [TestStepFail](CAPLfunctionTestStep.md) • [TestStepPass](CAPLfunctionTestStep.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
