[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestReportAddMiscInfoBlock.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestReportAddMiscInfoBlock

# TestReportAddMiscInfoBlock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`TestReportAddMiscInfoBlock (char title[]);`

## Description

The function generates a new information block for additional information pairs in the report. With the function [TestReportAddMiscInfo](CAPLfunctionTestReportAddMiscInfo.md) information pairs can be taken up into this block. This is possible until a new information block is opened with TestReportAddMiscInfoBlock, the current test case is ended (if the information block was opened within the test case) or a test case is called (if the information block was called in the test module).

## Parameters

- **title**: Title of the information block.

## Return Values

—

## Example

See example: [TestReportAdd* Functions](CAPLfunctionsTFSExampleTestReportAddFunctions.md)

[TestReportAddMiscInfo](CAPLfunctionTestReportAddMiscInfo.md) • [TestReportAddExtendedInfo](CAPLfunctionTestReportAddExtendedInfo.md) • [TestReportAddEngineerInfo](CAPLfunctionTestReportAddEngineerInfo.md) • [TestReportAddSetupInfo](CAPLfunctionTestReportAddEngineerInfo.md) • [TestReportAddSUTInfo](CAPLfunctionTestReportAddEngineerInfo.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)