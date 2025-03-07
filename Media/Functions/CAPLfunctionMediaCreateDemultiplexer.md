[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaCreateDemultiplexer.md)

# MediaCreateDemultiplexer

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » MediaCreateDemultiplexer

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword MediaCreateDemultiplexer(char inputSubtype[])
```

## Description

Creates a demultiplexer for the provided input media subtype. For a list of subtypes, [Major Media Types / Subtypes](../CAPLfunctionsMediaMajorMediaTypesSubtypes.md).

## Parameters

- **inputSubtype**: The media subtype describing the format of the input (multiplex) stream. Currently supported subtype: **StreamFormat_MPEG2Transport**. The Major Type for multiplex streams is always **MajorType_Stream**.

## Return Values

- **0**: The function failed. Call [MediaGetLastError](CAPLfunctionMediaGetLastError.md) to get a more specific error code.
- **≠0**: Demultiplexer handle.

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)