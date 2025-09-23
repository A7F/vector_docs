# MediaCreateMultiplexer

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » MediaCreateMultiplexer

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword MediaCreateMultiplexer(char outputSubtype[])
```

## Description

Creates a multiplexor for the provided output media subtype. For a list of subtypes, see [Major Media Types / Subtypes](../CAPLfunctionsMediaMajorMediaTypesSubtypes.md).

## Parameters

- **outputSubtype**: The media subtype describing the format of the output (multiplex) stream. Currently supported subtype: **StreamFormat_MPEG2Transport**. The Major Type for multiplex streams is always **MajorType_Stream**.

## Return Values

- **0**: The function failed. Call [MediaGetLastError](CAPLfunctionMediaGetLastError.md) to get a more specific error code.
- **≠0**: Multiplexer handle.

## Example

—
