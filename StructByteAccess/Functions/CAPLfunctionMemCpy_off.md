[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/StructByteAccess/Functions/CAPLfunctionMemCpy_off.md)

## CAPL Functions » Struct Byte Access » memcpy_off

### Function Syntax

- `void memcpy_off( struct type dest, dword destOffset, byte source[], dword sourceOffset, dword length); // form 1`
- `void memcpy_off( struct type dest, dword destOffset, char source[], dword sourceOffset, dword length); // form 2`
- `void memcpy_off( byte dest[], dword destOffset, struct type source, dword sourceOffset, dword length); // form 3`
- `void memcpy_off( char dest[], dword destOffset, struct type source, dword sourceOffset, dword length); // form 4`
- `void memcpy_off( byte dest[], dword destOffset, byte source[], dword sourceOffset, dword length); // form 5`
- `void memcpy_off( char dest[], dword destOffset, byte source[], dword sourceOffset, dword length); // form 6`
- `void memcpy_off( byte dest[], dword destOffset, char source[], dword sourceOffset, dword length); // form 7`
- `void memcpy_off( char dest[], dword destOffset, char source[], dword sourceOffset, dword length); // form 8`
- `void memcpy_off( struct dest, dword destOffset, char source[], dword sourceOffset, dword length); // form 9`
- `void memcpy_off( union dest, dword destOffset, char source[], dword sourceOffset, dword length); // form 10`
- `void memcpy_off( array dest, dword destOffset, char source[], dword sourceOffset, dword length); // form 11`
- `void memcpy_off( byte[] dest, dword destOffset, struct source, dword sourceOffset, dword length); // form 12`
- `void memcpy_off( byte[] dest, dword destOffset, union source, dword sourceOffset, dword length); // form 13`
- `void memcpy_off( byte[] dest, dword destOffset, array source, dword sourceOffset, dword length); // form 14`

### Description

Copies bytes from a source to destination, giving a destination start offset. The size of the destination must be at least `destOffset + length`.

### Parameters

- **dest**: 
  - (form 1, 2): Struct into which the bytes shall be copied.
  - (form, 9, 10, 11): vCDL object into which the bytes shall be copied.
  - (other forms): Array into which the bytes shall be copied.

- **source**: 
  - (form 3, 4): Struct from which the bytes shall be copied.
  - (form 12, 13, 14): vCDL object from which the bytes shall be copied.
  - (other forms): Array from which the bytes shall be copied.

- **destOffset**: Start offset in the destination struct or array.

- **sourceOffset**: Start offset in the source struct or array.

- **length**: Number of bytes which shall be copied.

### Return Values

—

### Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)