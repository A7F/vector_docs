[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionMpeg4CurrentSampleEntry.md)

**CAPL Functions** » [Media API](../CAPLfunctionsMediaOverview.md) » [Properties](../CAPLfunctionsMediaProperties.md) » Mpeg4CurrentSampleEntry

# Mpeg4CurrentSampleEntry

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Property

Mpeg4CurrentSampleEntry

## Description

Specifies the current entry in the sample description box for an MPEG-4 media type.

## Data Type

dword

## Remarks

- In an MP4 or 3GP file, the sample description box describes the encoding used for a stream in the file. The sample description box can contain multiple entries. This property specifies which entry to use. The value is a zero-based index into the list.
- Currently, the only supported value is 0. The property has been defined for future extensibility.
- The MPEG-4 file source always sets the value to 0. The MP4 and 3GP file sinks ignore the value of this property if it is present.

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
