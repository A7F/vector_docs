[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaEnumAudioCapturers.md)

**CAPL Functions** » **Media API** » **MediaEnumAudioCapturers**

# MediaEnumAudioCapturers

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```
dword MediaEnumAudioCapturers(dword& count, dword audioCapturerHandles[]);
```

## Description

Enumerates a list of audio capture devices.

## Parameters

- **count**: Count of elements provided in **audioCapturerHandles**.  
  Caller: Set to elCount(**audioCapturerHandles**).  
  On successful return of the function this parameter contains the number of valid handles in the **audioCapturerHandles** array.

- **audioCapturerHandles**: Array in which this function returns the audio capturer handles of all audio capture devices that are available. After its use, the caller must release each audio capturer returned in the array by calling [MediaReleaseAudioCapturer](CAPLfunctionMediaReleaseAudioCapturer.md).

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions)** Version **18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
