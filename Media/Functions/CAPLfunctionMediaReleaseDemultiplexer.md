# MediaReleaseDemultiplexer

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » MediaReleaseDemultiplexer

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaReleaseDemultiplexer(dword demultiplexerHandle);
```

## Description

Releases a demultiplexer.

## Parameters

- **demultiplexerHandle**: The multiplexer handle returned previously by a call to [MediaCreateDemultiplexer](CAPLfunctionMediaCreateDemultiplexer.md).

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md).

## Example

—
