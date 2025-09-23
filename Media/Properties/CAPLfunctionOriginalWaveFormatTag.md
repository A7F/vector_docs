# OriginalWaveFormatTag

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

OriginalWaveFormatTag

## Description

Contains the original WAVE format tag for an audio stream.

## Data Type

dword

## Remarks

- Depending on the source file, the AVI media source might set this property on the media types that it offers.
- An AVI file contains a stream header for each stream in the file. The AVI media source translates the stream header into a media type. For audio streams, the stream header contains a format tag that identifies the audio format. In most cases, the AVI media source converts the format tag directly to a subtype, see [Audio Subtypes](../CAPLfunctionsMediaMajorMediaTypesSubtypes.md). In some cases, however, it maps the original format tag to another format tag that is equivalent. If so, the media source stores the original format tag in the media type, using the **OriginalWaveFormatTag** property.
- The format mappings are stored in the Registry under the following key:

  `HKEY_CLASSES_ROOT\MediaFoundation\MapAudioFormatTag`

- Each entry is a dword value. The name of the entry is the decimal representation of the format tag. The value of the entry is the equivalent format tag.

[See Also](javascript:void(0);)
