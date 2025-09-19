[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783fswritefile.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783FSWriteFile

# Iso11783FSWriteFile

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long Iso11783FSWriteFile( dword fileHandle, dword bufferSize, char buffer[] );
long Iso11783FSWriteFile( dword fileHandle, dword bufferSize, byte buffer[] );
```

## Description

This function writes data to an open file.

**Note:** Contrary to the other file operations, this function does not provide any functionality for a passed directory handle.

## Parameters

- **fileHandle**: File handle, see also [Iso11783FSOpenFile](CAPLfunctionIso11783FSOpenFile.md)
- **bufferSize**: Number of bytes to write
- **buffer**: Data to write

## Return Values

- **< 0**: [error code](../CAPLfunctionsISONLErrorCodes.md)
- **≥ 0**: number of written bytes

## Example

```c
LONG handle;
char data[200];

handle = Iso11783FSOpenFile( "\test.TXT", 0x02 );
if (handle > 0) {
  Iso11783FSWriteFile( handle, 12, "Hello World!" );
  Iso11783FSCloseFile( handle );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
