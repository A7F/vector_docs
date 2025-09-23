[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783fsseekfile.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783FSSeekFile

# Iso11783FSSeekFile

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783FSSeekFile( dword fileHandle, dword mode, dword offset );
```

## Description

This function moves the current write/read position of an open file or the read position of directory entries within a directory.

## Parameters

- **fileHandle**: File or directory handle, see also [Iso11783FSOpenFile](CAPLfunctionIso11783FSOpenFile.md)
- **mode**:
  - 0: from the beginning of the file / from the first directory entry
  - 1: from the current pointer position
  - 2: from the end of the file / from the last directory entry
- **offset**: Number of bytes to move the file pointer or the number of directory entries to move the directory pointer

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783FSSeekFile( handle, 0, 10 );
```
