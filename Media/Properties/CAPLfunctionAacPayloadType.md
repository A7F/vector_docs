# AacPayloadType

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

AacPayloadType

## Description

Specifies the payload type of an Advanced Audio Coding (AAC) stream.

## Data Type

dword

The following values are possible:

- 0: The stream contains raw_data_block elements only.
- 1: Audio Data Transport Stream (ADTS). The stream contains an adts_sequence, as defined by MPEG-2.
- 2: Audio Data Interchange Format (ADIF). The stream contains an adif_sequence, as defined by MPEG-2.
- 3: The stream contains an MPEG-4 audio transport stream with a synchronization layer (LOAS) and a multiplex layer (LATM).

## Remarks

**AacPayloadType** is optional. If this property is not specified, the default value 0 is used, which specifies the stream contains raw_data_block elements only.

Applies only to AudioFormat_AAC.

[See Also](javascript:void(0);)
