# AudioValidBitsPerSample

**Valid for**: CANoe DE • CANoe4SW DE

## Property

AudioValidBitsPerSample

## Description

Number of valid bits of audio data in each audio sample.

## Data Type

dword

## Remarks

The **AudioValidBitsPerSample** property is used for audio formats that contain padding after each audio sample. The total size of each audio sample, including padding bits, is given in the [AudioBitsPerSample](CAPLfunctionAudioBitsPerSample.md) property.  
If the **AudioValidBitsPerSample** property is not set, use the [AudioBitsPerSample](CAPLfunctionAudioBitsPerSample.md) property to find the number of valid bits per sample.  
If an audio format does not contain any padding bits, then this property should not be set, or should be set to the same value as the [AudioBitsPerSample](CAPLfunctionAudioBitsPerSample.md) property.
