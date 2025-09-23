# MediaGetInputType

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » MediaGetInputType

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword MediaGetInputType(dword de-/multiplexerHandle, dword inputStreamIndex);
```

## Description

Retrieves the media type of a stream the de-/multiplexer takes as input.

## Parameters

- **de-/multiplexerHandle**: The de-/multiplexer handle returned previously by a call to [MediaCreateMultiplexer](CAPLfunctionMediaCreateMultiplexer.md)/[MediaCreateDemultiplexer](CAPLfunctionMediaCreateDemultiplexer.md).

- **inputStreamIndex**: The index of the output stream the media type should be retrieved for. For demultiplexers set to 0.

## Return Values

- **0**: The function failed. Call [MediaGetLastError](CAPLfunctionMediaGetLastError.md) to get a more specific error code.

- **≠0**: Media type handle.

## Example

—
