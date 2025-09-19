[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGroupBegin.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGroupBegin

# TestGroupBegin

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `TestGroupBegin (char title[], char description[]);` // form 1
- `TestGroupBegin (char ident[], char title[], char description[]);` // form 2

## Description

A test group is opened with this function. It may only be called in a test module, but not in a test case. All test cases and test groups that are executed before call of the corresponding function [TestGroupEnd](CAPLfunctionTestGroupEnd.md) are part of this test group. If a test group is not closed with [TestGroupEnd](CAPLfunctionTestGroupEnd.md), then at the end of the test module, a warning is written in the Write Window and the test group is closed automatically.

To obtain line breaks (in form of `<br />` tags) in the test report, "\n" may be inserted at any place.

## Parameters

- **ident**: E.g. a test group number) of the test group.
- **title**: Title for the test group.
- **description**: Description text for the test group.

## Return Values

—

## Example

See example: [TestGroupBegin, TestGroupEnd](CAPLfunctionsTFSExampleTestGroupBeginTestGroupEnd.md)

[TestGroupEnd](CAPLfunctionTestGroupEnd.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
