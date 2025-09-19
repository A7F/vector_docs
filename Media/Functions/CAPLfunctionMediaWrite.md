[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaWrite.md)

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » MediaWrite

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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
