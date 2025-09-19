[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestReportAddMiscInfo.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestReportAddMiscInfo

# TestReportAddMiscInfo

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`TestReportAddMiscInfo (char name[], char description[], ...);`

## Description

With these functions, information pairs of name and description (e.g. "parameter value V0" and "3.7 V") can be taken up into an additional information area in the report. The additional information area must be created previously with [TestReportAddMiscInfoBlock](CAPLfunctionTestReportAddMiscInfoBlock.md). If this function is used and there is no corresponding information area, then a warning will be generated in the Write Window and a new information area will be created automatically. In this information area, any number of information pairs can be written with this function.

## Parameters

The format string has the same meaning as with the [write](../../Other/Functions/CAPLfunctionWrite.md) function and is described there.

- **name**: Information pair of name and description.
- **description**: Information pair of name and description.

## Return Values

—

## Example

See example: [TestReportAdd* Functions](CAPLfunctionsTFSExampleTestReportAddFunctions.md)

[TestReportAddMiscInfoBlock](CAPLfunctionTestReportAddMiscInfoBlock.md) • [TestReportAddExtendedInfo](CAPLfunctionTestReportAddExtendedInfo.md) • [TestReportAddEngineerInfo](CAPLfunctionTestReportAddEngineerInfo.md) • [TestReportAddSetupInfo](CAPLfunctionTestReportAddEngineerInfo.md) • [TestReportAddSUTInfo](CAPLfunctionTestReportAddEngineerInfo.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
