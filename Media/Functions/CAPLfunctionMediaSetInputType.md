[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaSetInputType.md)

**CAPL Functions** » [Media API](../CAPLfunctionsMediaOverview.md) » MediaSetInputType

# MediaSetInputType

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaSetInputType(dword de-/multiplexerHandle, dword inputStreamIndex, dword mediaTypeHandle)
```

## Description

Sets the input media type for a de-/multiplexer at a given index.

## Parameters

- **de-/multiplexerHandle**: The de-/multiplexer handle returned previously by a call to [MediaCreateMultiplexer](CAPLfunctionMediaCreateMultiplexer.md)/[MediaCreateDemultiplexer](CAPLfunctionMediaCreateDemultiplexer.md).
- **inputStreamIndex**: The index of the input stream the media type should be set for. Currently only 1 input stream per multiplex stream is supported, so set this parameter to 0. For demultiplexers set to 0.
- **mediaTypeHandle**: The handle of the media type describing the format of the input stream.

## Return Values

- **0**: The function succeeded
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—
