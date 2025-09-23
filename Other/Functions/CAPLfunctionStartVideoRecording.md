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
