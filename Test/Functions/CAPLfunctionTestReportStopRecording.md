[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestReportStopRecording.md)

**CAPL Functions** » **Test Feature Set** » **TestReportStopRecording**

# TestReportStopRecording

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**: This function can only be used in test units with report configured to use Test Report Viewer format.

## Function Syntax

- `testReportStopRecording(signal aSignal);`
- `testReportStopRecording(sysvar aSysVar);`
- `testReportStopRecording(valueHandle* aDOMember);`

## Description

Stops the recording of the symbol in the test report. If the recording is not explicitly stopped it will be automatically stopped at the end of the test unit (or at the end of each execution cycle, respectively).

## Parameters

- **aSignal**: The signal to be stopped recording.
- **aSysVar**: The system variable to be stopped recording.
- **aDOMember**: The distributed object member to be stopped recording.

## Return Values

—

## Example

```plaintext
testReportStartRecording(comfort::VehicleMotion::CrashDetected, "Signal1");

// … do something

testReportStopRecording(comfort::VehicleMotion::CrashDetected);
```

[TestReportStartRecording](CAPLfunctionTestReportStartRecording.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
