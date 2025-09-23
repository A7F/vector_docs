# MediaReleaseMultiplexer

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long MediaReleaseMultiplexer(dword multiplexerHandle)
```

## Description

Releases a multiplexer.

## Parameters

- **multiplexerHandle**: The multiplexer handle returned previously by a call to [MediaCreateMultiplexer](CAPLfunctionMediaCreateMultiplexer.md).

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md).

## Example

—
