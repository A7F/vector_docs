# TestReportAddEngineerInfo, TestReportAddSetupInfo, TestReportAddSUTInfo

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `TestReportAddEngineerInfo (char name[], char description[], ...);`
- `TestReportAddSetupInfo (char name[], char description[], ...);`
- `TestReportAddSUTInfo (char name[], char description[], ...);`

## Description

With these functions, information pairs of name and description (e.g. "serial number" and "S012345AB") can be taken up into the report in the areas **TestEngineer**, **TestSetUp**, and **device (SUT)** to be tested. The three areas named must not be created; they are automatically available in the report. In the course of the test execution, any number of information pairs can be written.

## Parameters

The format string has the same meaning as with the [write](../../Other/Functions/CAPLfunctionWrite.md) function and is described there.

- **name**: Information pair of name and description.
- **description**: Information pair of name and description.

## Return Values

—

## Example

See example: [TestReportAdd* Functions](CAPLfunctionsTFSExampleTestReportAddFunctions.md)

[TestReportAddMiscInfoBlock](CAPLfunctionTestReportAddMiscInfoBlock.md) • [TestReportAddMiscInfo](CAPLfunctionTestReportAddMiscInfo.md) • [TestReportAddExtendedInfo](CAPLfunctionTestReportAddExtendedInfo.md)
