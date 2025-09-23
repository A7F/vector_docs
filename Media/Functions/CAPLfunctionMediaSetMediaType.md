# MediaSetMediaType

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaSetMediaType(dword sourceReaderOrSinkWriterHandle, dword streamIndex, dword mediaTypeHandle);
```

## Description

Sets the media type for a source reader or a sink writer.

- **Source reader**: This media type defines the format that the source reader produces as output (retrievable via [MediaRead](CAPLfunctionMediaRead.md)). It can differ from the native format provided by the media source. The source reader tries to set the media type as the native media type of the media source first. If that fails, it tries to load an appropriate decoder which – if available – can do the format conversion.

- **Sink writer**: This media type defines the format that the sink writer expects as input to its [MediaWrite](CAPLfunctionMediaWrite.md) function. It can differ from the native format provided by the media sink. The sink writer tries to set the media as the native media type of the media sink first. If that fails, it tries to load an appropriate encoder, which – if available – can do the format conversion.

## Parameters

- **mediaTypeHandle**: The media type handle.

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)
