# MediaGetOutputType

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » MediaGetOutputType

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```
dword MediaGetOutputType(dword de-/multiplexerHandle, dword outputStreamIndex)
```

## Description

Retrieves the media type of a stream the de-/multiplexer produces as output at a given index.

## Parameters

- **de-/multiplexerHandle**: The de-/multiplexer handle returned previously by a call to [MediaCreateMultiplexer](CAPLfunctionMediaCreateMultiplexer.md)/[MediaCreateDemultiplexer](CAPLfunctionMediaCreateDemultiplexer.md).
- **outputStreamIndex**: The index of the output stream the media type should be retrieved for. For multiplexers set to 0.

## Return Values

- **0**: The function failed. Call [MediaGetLastError](CAPLfunctionMediaGetLastError.md) to get a more specific error code.
- **≠0**: Media type handle.

## Example

—
