[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/StructByteAccess/Functions/CAPLfunctionMemCmp.md)

# memcmp

[CAPL Functions](../../CAPLfunctions.md) » [Struct Byte Access](../CAPLfunctionsStructByteAccessOverview.md) » memcmp

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `int memcmp(struct * dest, byte source[]); // form 1`
- `int memcmp(byte dest[], struct * source); // form 2`
- `int memcmp(struct * dest, struct * source); // form 3`
- `int memcmp(byte dest[], byte source[], dword size); // form 4`
- `int memcmp(struct dest, struct source); // form 5`
- `int memcmp(array dest, array source); // form 6`
- `int memcmp(union dest, union source); // form 7`
- `int memcmp(struct dest, byte source[]); // form 8`
- `int memcmp(array dest, byte source[]); // form 9`
- `int memcmp(union dest, byte source[]); // form 10`
- `int memcmp(byte dest[], struct source); // form 11`
- `int memcmp(byte dest[], array source); // form 12`
- `int memcmp(byte dest[], union source); // form 13`

## Description

Compares the bytes of the parameters.  
In form 3, both structs must have the same type.  
Forms 5-13 compare vCDL objects with themselves or byte arrays.  
In form 5-7, dest and source must have the same type.  
In form 8-13, the vCDL object must have a fixed layout.

## Parameters

- **dest**: A struct / byte array / vCDL object
- **source**: Another struct / byte array / vCDL object
- **size**: Size of the arrays (number of bytes to compare).

## Return Values

0 if the bytes are equal; a value different from 0 if they are unequal

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
dwordWrapper.dw = 0x03020100;
if (memcmp(dwordWrapper, data) == 0)
   write("Data represents the number: Little Endian is used.");
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)