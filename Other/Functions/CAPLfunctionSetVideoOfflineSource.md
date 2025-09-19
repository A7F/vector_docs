[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetVideoOfflineSource.md)

**CAPL Functions** » **General** » **Function Overview** » **SetVideoOfflineSource**

# SetVideoOfflineSource

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**: This function is only allowed in [on preStart](../CAPLfunctionsEventProceduresOverview.md) event procedure.

## Function Syntax

```
SetVideoOfflineSource(char windowName[], long sourceType, char sourcePath[]);
```

## Description

Sets the offline source (type and path) for a CANoe DE product [Video Window](../../../CANoeCANalyzer/Windows/Video/VideoWindow.md).

## Parameters

- **windowName**: The name of the Video Window.
- **sourceType**: The type of offline source:
  - `0|cNoVideoInput`
  - `1|cVideoFile`
  - `2|cImageFolder`

  For details see the **Offline Source** in the CANoe DE product [Video Configuration](../../../CANoeCANalyzer/Windows/Video/VideoWindowConfiguration.md) dialog.

- **sourcePath**: The corresponding source path:
  - For **cNoVideoInput** the path will be ignored.
  - For **cVideoFile** this must be an existing video file.
  - For **cImageFolder** this must be an existing folder.

## Return Values

—

## Example

```plaintext
on preStart
{
  // Configure offline source (video file)
  SetVideoOfflineSource("Video Window", 1, "MyVideoFile.avi");
}
```

**Related Links**: [SetVideoOfflineLoggerCam](CAPLfunctionSetVideoOfflineLoggerCam.md) • [SetVideoRecordFile](CAPLfunctionSetVideoRecordFile.md) • [SetVideoTriggerTimes](CAPLfunctionSetVideoTriggerTimes.md) • [StartVideoRecording](CAPLfunctionStartVideoRecording.md) • [StopVideoRecording](CAPLfunctionStopVideoRecording.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
