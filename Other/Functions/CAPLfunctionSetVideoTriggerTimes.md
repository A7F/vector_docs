[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetVideoTriggerTimes.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » SetVideoTriggerTimes

# SetVideoTriggerTimes

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This function is only allowed in [on preStart](../CAPLfunctionsEventProceduresOverview.md) event procedure.

## Function Syntax

```
SetVideoTriggerTimes(char windowName[], dword preTriggerTime, dword postTriggerTime);
```

## Description

Sets the trigger times for a CANoe DE product [Video Window](../../../CANoeCANalyzer/Windows/Video/VideoWindow.md).

## Parameters

- **windowName**: The name of the Video Window.
- **preTriggerTime**: The pre trigger time (in ms). For details see the pre trigger time in the CANoe DE product [Video Configuration](../../../CANoeCANalyzer/Windows/Video/VideoWindowConfiguration.md) dialog.
- **postTriggerTime**: The post trigger time (in ms). For details see the post trigger time in the CANoe DE product [Video Configuration](../../../CANoeCANalyzer/Windows/Video/VideoWindowConfiguration.md) dialog.

## Return Values

—

## Example

```c
// set trigger times for "VideoWindow"
SetVideoTriggerTimes("VideoWindow", 0, 2500);
```

[SetVideoOfflineLoggerCam](CAPLfunctionSetVideoOfflineLoggerCam.md) • [SetVideoOfflineSource](CAPLfunctionSetVideoOfflineSource.md) • [SetVideoRecordFile](CAPLfunctionSetVideoRecordFile.md) • [StartVideoRecording](CAPLfunctionStartVideoRecording.md) • [StopVideoRecording](CAPLfunctionStopVideoRecording.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)