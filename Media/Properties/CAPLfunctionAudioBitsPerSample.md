# AudioBitsPerSample

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Property

AudioBitsPerSample

## Description

Number of bits per audio sample in an audio media type.

## Data Type

dword

## Remarks

If some bits contain padding, set the [AudioValidBitsPerSample](CAPLfunctionAudioValidBitsPerSample.md) property to specify the number of bits of valid audio data in each sample.  
If the audio contains 8 bits per sample, the audio samples are unsigned values (each audio sample has the range 0–255).  
If the audio contains 16 bits per sample or higher, the audio samples are signed values.
