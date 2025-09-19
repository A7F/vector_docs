[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/StructByteAccess/Functions/CAPLfunctionMemCpy.md)

[CAPL Functions](../../CAPLfunctions.md) » [Struct Byte Access](../CAPLfunctionsStructByteAccessOverview.md) » memcpy

# memcpy

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void memcpy(byte dest[], struct * source); // form 1`
- `void memcpy(char dest[], struct * source); // form 2`
- `void memcpy(byte dest[], long offset, struct * source); // form 3`
- `void memcpy(char dest[], long offset, struct * source); // form 4`
- `void memcpy(struct * dest, byte source[]); // form 5`
- `void memcpy(struct * dest, char source[]); // form 6`
- `void memcpy(struct * dest, byte source[], long offset); // form 7`
- `void memcpy(struct * dest, char source[], long offset); // form 8`
- `void memcpy(struct * dest, struct * source); // form 9`
- `void memcpy(byte dest[], byte source[], dword length); // form 10`
- `void memcpy(byte dest[], char source[], dword length); // form 11`
- `void memcpy(char dest[], byte source[], dword length); // form 12`
- `void memcpy(char dest[], char source[], dword length); // form 13`
- `void memcpy(struct dest, char source[]); // form 14`
- `void memcpy(struct dest, byte source[]); // form 15`
- `void memcpy(char dest[], struct source); // form 16`
- `void memcpy(byte dest[], struct source); // form 17`
- `void memcpy(PDUPayload dest, PDUPayload source, dword length); // form 18`
- `void memcpy(PDUPayload dest, byte source[], dword length); // form 19`
- `void memcpy(byte source[], PDUPayload dest, dword length); // form 20`
- `void memcpy(PDUPayload dest, struct * source); // form 21`
- `void memcpy(struct * dest, PDUPayload source); // form 22`
- `void memcpy(bytes dest, byte source[]); // form 23`
- `void memcpy(bytes dest, char source[]); // form 24`
- `void memcpy(bytes dest, byte source[], dword length); // form 25`
- `void memcpy(bytes dest, char source[], dword length); // form 26`
- `void memcpy(byte dest[], bytes source); // form 27`
- `void memcpy(char dest[], bytes source); // form 28`

## Description

Copies bytes from a source to a destination. In form 9, both structs must have the same type. In other forms with structs, the arrays must be large enough to contain the struct data. In forms 18 to 22, the payload size and the struct size must be identical.

## Parameters

- **source**
  - (form 1-4, 9, 16, 17, 21): Struct whose bytes shall be copied.
  - (form 18, 22): Payload data of a PDU whose bytes shall be copied.
  - (form 27, 28): vCDL "bytes" value that shall be copied.
  - (other forms): Array whose bytes shall be copied.

- **dest**
  - (form 5, 6, 7, 8, 9, 22): Struct into which the bytes shall be copied.
  - (form 18, 19, 20, 21): Payload data of a PDU into which the bytes shall be copied.
  - (form 23, 24, 25, 26): vCDL "bytes" value into which the bytes shall be copied.
  - (other forms): Array into which the bytes shall be copied.

- **offset**
  - (form 3, 4, 7, 8): Offset in the array which marks the start of the data.

- **length**
  - (form 10, 11, 12, 13, 18, 19, 20, 25, 26): number of bytes which shall be copied.

## Return Values

—

## Example

```c
byte data[4];
struct WrapDword
{
   dword dw;
} dwordWrapper;

int i;
for (i = 0; i < elcount(data); ++i)
   data[i] = i;
memcpy(dwordWrapper, data);
write("Bytes as dword: %0#10lx", dwordWrapper.dw);
dwordWrapper.dw = 0x12345678;
memcpy(data, dwordWrapper);
write("dword as bytes: %#lx %#lx %#lx %#lx", data[0], data[1], data[2], data[3]);
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
