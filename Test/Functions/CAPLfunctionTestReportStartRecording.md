[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestReportStartRecording.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestReportStartRecording

# TestReportStartRecording

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This function can only be used in test units with report configured to use Test Report Viewer format.

## Function Syntax

- `testReportStartRecording(signal aSignal);`
- `testReportStartRecording(signal aSignal, char alias[]);`
- `testReportStartRecording(sysvar aSysVar);`
- `testReportStartRecording(sysvar aSysVar, char alias[]);`
- `testReportStartRecording(valueHandle* aDOMember);`
- `testReportStartRecording(valueHandle* aDOMember, char alias[]);`

## Description

Starts the recording of a symbol in the test report. Optionally, an alias for the symbol to show in the test report instead of the symbol name can be set. If the recording is not explicitly stopped it will be automatically stopped at the end of the test unit (or at the end of each execution cycle, respectively).

## Parameters

- **aSignal**: The signal to be recorded.
- **aSysVar**: The system variable to be recorded.
- **aDOMember**: The distributed object member to be recorded.
- **alias**: The alias to show instead of the symbol name.

## Return Values

—

## Example

```plaintext
testReportStartRecording(comfort::VehicleMotion::CrashDetected, "Signal1");

// … do something

testReportStopRecording(comfort::VehicleMotion::CrashDetected);
```

[TestReportStopRecording](CAPLfunctionTestReportStopRecording.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
