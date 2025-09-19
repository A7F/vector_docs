[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionArbitraryHeader.md)

**CAPL Functions** » **Media API** » **Properties** » **ArbitraryHeader**

# ArbitraryHeader

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Property

ArbitraryHeader

## Description

Type-specific data for a binary stream in an Advanced Systems Format (ASF) file.

## Data Type

byte[]

## Remarks

ASF files can contain streams with binary data. The **ArbitraryHeader** property in the media type contains a structure that describes the stream.

In addition to the **ArbitraryHeader** property, the media type for an ASF binary stream contains the properties [MajorType](CAPLfunctionMajorType.md) and [ArbitraryFormat](CAPLfunctionArbitraryFormat.md).

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
