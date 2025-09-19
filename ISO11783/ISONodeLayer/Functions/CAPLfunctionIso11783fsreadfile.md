[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783fsreadfile.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783FSReadFile

# Iso11783FSReadFile

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783FSReadFile( dword fileHandle, dword bufferSize, char buffer[] );
long Iso11783FSReadFile( dword fileHandle, dword bufferSize, byte buffer[] );
long Iso11783FSReadFile( dword fileHandle, dword bufferSize, char buffer[], long flags);
long Iso11783FSReadFile( dword fileHandle, dword bufferSize, byte buffer[], long flags);
```

## Description

The function reads data from an open file and directory entries from an open directory respectively.

Whenever reading directory entries, ensure that `handle` consists of at least (n * 22 + 2) bytes (n = the number of directory entries to read passed in `size`. 22 bytes is a maximum length directory entry when the filename length is 12 characters (subject to the 8.3 naming convention). Two bytes are used for the word in `buffer[0]` and `buffer[1]` with the number of directory entries actually read).

## Parameters

- **fileHandle**: File or directory handle, see also [Iso11783FSOpenFile](CAPLfunctionIso11783FSOpenFile.md)
- **bufferSize**: Size of `buffer` in Bytes (`handle` references file) or number of directory entries to read (`handle` references directory)
- **buffer**: The read data is copied into this buffer. The word space consisting of `buffer[0]` (low byte) and `buffer[1]` (high byte) contains the number of read data bytes from the file (handle references file) or the number of read directory entries (handle references directory) respectively.

  **Structure of a directory entry:**
  - Byte 1: length (bytes) of the file or directory name
  - Byte 2-n: file or directory name
  - Byte n+1: attributes (see [Iso11783GetFileInfo](CAPLfunctionIso11783fsgetfileinfo.md))
  - Bytes n+2, n+3: date
    - bits 1..5: day
    - bits 6..9: month
    - bits 10..16: year-1989
  - Bytes m+4, n+5: time
    - bits 1..5: seconds/2
    - bits 6..11: minutes
    - bits 12..16: hours
  - Bytes n+6..n+9: size of the file/directory

- **flags**: Bit 0: if this bit is set hidden files are listed during reading directories

## Return Values

- **≥ 0**: number of bytes written to buffer
- **< 0**: [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
// Read data from file
LONG handle;
char data[200];

handle = Iso11783FSOpenFile( "\test.TXT", 0x00 );
if (handle > 0) {
  Iso11783FSReadFile( handle, elCount(data), data );
  Iso11783FSCloseFile( handle );
}

// Read directory entries:
LONG handle;
char data[200];

handle = Iso11783FSOpenFile( "\DIR1", 0x03 );
if (handle > 0) {
  Iso11783FSReadFile( handle, (elCount(data)-2)/22, data );
  Iso11783FSCloseFile( handle );
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
