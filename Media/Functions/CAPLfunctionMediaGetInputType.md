[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaGetInputType.md)

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
