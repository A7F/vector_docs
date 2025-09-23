# TestReportWriteDiagObject, TestReportWriteDiagResponse

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `TestReportWriteDiagObject (diagRequest req);`
- `TestReportWriteDiagObject (diagResponse resp);`
- `TestReportWriteDiagResponse (diagRequest req);`

## Description

`TestReportWriteDiagObject` writes a test step with a textual interpretation of the specified request or response object into the test report.

`TestReportWriteDiagResponse` writes a test step with a textual interpretation of the received response for the specified request object into the test report.

These test steps are subject to the common test step report filtering as configured in the **Test Module Configuration** dialog.

## Parameters

- **req**: Request
- **resp**: Response

## Return Values

[Error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md)

## Example

[Using Diagnostics Functions in Test Cases](../../Diagnostics/CAPLfunctionsDiagnosticsUsingFunctionTestCase.md)

[Test Feature Set CAPL Functions](../CAPLfunctionsTFSOverview.md)
