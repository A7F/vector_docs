[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStartVideoRecording.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » StartVideoRecording

# StartVideoRecording

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
StartVideoRecording(char windowName[]);
```

## Description

Starts/resumes the recording for a CANoe DE product [Video Window](../../../CANoeCANalyzer/Windows/Video/VideoWindow.md).

## Parameters

- **windowName**: The name of the Video Window.

## Return Values

—

## Example

```c
// start/resume the recording for "VideoWindow"
StartVideoRecording("VideoWindow");
```

[SetVideoOfflineLoggerCam](CAPLfunctionSetVideoOfflineLoggerCam.md) • [SetVideoOfflineSource](CAPLfunctionSetVideoOfflineSource.md) • [SetVideoRecordFile](CAPLfunctionSetVideoRecordFile.md) • [SetVideoTriggerTimes](CAPLfunctionSetVideoTriggerTimes.md) • StartVideoRecording

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
