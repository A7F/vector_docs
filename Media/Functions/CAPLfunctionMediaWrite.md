# MediaWrite

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaWrite(dword sinkWriterHandle, dword streamIndex, int64 timestamp, byte buffer[], dword length);
long MediaWrite(dword sinkWriterHandle, dword streamIndex, int64 timestamp, int buffer[], dword length);
long MediaWrite(dword sinkWriterHandle, dword streamIndex, int64 timestamp, long buffer[], dword length);
```

## Description

Delivers sample data to the sink writer. The buffer can be reused immediately after the function returns.

## Parameters

- **sinkWriterHandle**: The sink writer handle.
- **streamIndex**: The zero-based index of the stream.
- **buffer**: The buffer used to store the sample data.
- **length**: The length of the data buffer.

## Return Values

- **0**: The function succeeded
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)
