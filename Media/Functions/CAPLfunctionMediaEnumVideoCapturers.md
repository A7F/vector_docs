[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaEnumVideoCapturers.md)

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » MediaEnumVideoCapturers

# MediaEnumVideoCapturers

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword MediaEnumVideoCapturers(dword[] retVideoCapturerHandles, dword &retCount);
```

## Description

Enumerates a list of video capture devices.

## Parameters

- **retCount**: Count of elements provided in **videoCapturerHandles**. On successful return, this parameter contains the number of valid handles in the **videoCapturerHandles** array.
  
- **retVideoCapturerHandles**: Array in which this function returns the video capturer handles of all available video capture devices. After use, release each audio capturer returned in the array by calling [MediaReleaseVideoCapturer](CAPLfunctionMediaReleaseVideoCapturer.md).

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)