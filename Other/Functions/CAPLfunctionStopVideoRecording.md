[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStopVideoRecording.md)

**CAPL Functions** » **General** » **Function Overview** » **StopVideoRecording**

# StopVideoRecording

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`StopVideoRecording(char windowName[]);`

## Description

Stops/suspends the recording for a CANoe DE product [Video Window](../../../CANoeCANalyzer/Windows/Video/VideoWindow.md).

## Parameters

- **windowName**: The name of the Video Window.

## Return Values

—

## Example

```c
// stop/suspend the recording for "VideoWindow"
StopVideoRecording("VideoWindow");
```

[SetVideoOfflineLoggerCam](CAPLfunctionSetVideoOfflineLoggerCam.md) • [SetVideoOfflineSource](CAPLfunctionSetVideoOfflineSource.md) • [SetVideoRecordFile](CAPLfunctionSetVideoRecordFile.md) • [SetVideoTriggerTimes](CAPLfunctionSetVideoTriggerTimes.md) • [StartVideoRecording](CAPLfunctionStartVideoRecording.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
