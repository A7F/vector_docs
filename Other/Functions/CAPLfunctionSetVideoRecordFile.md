# SetVideoRecordFile

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**: This function is only allowed in [on preStart](../CAPLfunctionsEventProceduresOverview.md) event procedure.

## Function Syntax

```
SetVideoRecordFile(char windowName[], char recordFile[]);
```

## Description

Sets the record file for a CANoe DE product [Video Window](../../../CANoeCANalyzer/Windows/Video/VideoWindow.md).

## Parameters

- **windowName**: The name of the Video Window.
- **recordFile**: The path to the record file. This parameter can be
  - an absolute path. All non-existing directories of the path will be created.
  - a relative path. In that case the record file will be placed in the path relative to the configuration file. All non-existing directories of the path will be created.
  - a single filename. In that case the record file will be placed in the directory of the current configuration file.

  The directories of the path must be separated by a backslash ("\"). The only filename extension supported is **.AVI**. If no extension is provided, the **.AVI** filename extension will be used automatically. If an invalid extension is provided the function will do nothing.

  **Note**:
  - If a valid path is provided the recorder will automatically be activated, even if it is deactivated in the CANoe DE product [Video Configuration](../../../CANoeCANalyzer/Windows/Video/VideoWindowConfiguration.md) dialog. If an empty string (" ") is provided as path, the recorder will automatically be deactivated, even if it is activated in the CANoe DE product [Video Configuration](../../../CANoeCANalyzer/Windows/Video/VideoWindowConfiguration.md) dialog.
  - Within a string literal a second backslash has to be set (see example below).

## Return Values

—

## Example

—

[SetVideoOfflineLoggerCam](CAPLfunctionSetVideoOfflineLoggerCam.md) • [SetVideoOfflineSource](CAPLfunctionSetVideoOfflineSource.md) • [SetVideoTriggerTimes](CAPLfunctionSetVideoTriggerTimes.md) • [StartVideoRecording](CAPLfunctionStartVideoRecording.md) • [StopVideoRecording](CAPLfunctionStopVideoRecording.md)
