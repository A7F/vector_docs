[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/StructByteAccess/Functions/CAPLfunctionMemCpyH2n.md)

## memcpy_h2n

[CAPL Functions](../../CAPLfunctions.md) » [Struct Byte Access](../CAPLfunctionsStructByteAccessOverview.md) » memcpy_h2n

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

- `void memcpy_h2n(byte dest[], struct source); // form 1`
- `void memcpy_h2n(byte dest[], int offset, struct source); // form 2`

### Description

Copies the bytes from the struct into the array, and translates the byte order of the elements from little-endian to big-endian (h2n stands for "host to network").

### Parameters

- **source**: Struct whose bytes shall be copied
- **dest**: Array into which the bytes shall be copied
- **offset (form 2)**: Offset into the array

### Return Values

—

### Example

```c
byte data[4];
struct WrapDword
{
   dword dw;
} dwordWrapper;

int i;
for (i = 0; i < elcount(data); ++i)
   data[i] = i;
memcpy_n2h(dwordWrapper, data);
write("Bytes as dword: %0#10lx", dwordWrapper.dw);
dwordWrapper.dw = 0x12345678;
memcpy_h2n(data, dwordWrapper);
write("dword as bytes: %#lx %#lx %#lx %#lx", data[0], data[1], data[2], data[3]);
```
