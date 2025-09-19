[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestReportStopAllRecordings.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestReportStopAllRecordings

# TestReportStopAllRecordings

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This function can only be used in test units with report configured to use Test Report Viewer format.

## Function Syntax

`testReportStopAllRecordings()`

## Description

Stops all currently running recordings in the test report. If recordings are not explicitly stopped they will be automatically stopped at the end of the test unit (or at the end of each execution cycle, respectively).

## Parameters

—

## Return Values

—

## Example

```plaintext
testReportStartRecording(comfort::VehicleMotion::CrashDetected, "Signal1");
testReportStartRecording(sysvar::Namespace1::SVTest);

// … do something

testReportStopAllRecordings();
```

[TestReportStartRecording](CAPLfunctionTestReportStartRecording.md) • [TestReportStopRecording](CAPLfunctionTestReportStopRecording.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
