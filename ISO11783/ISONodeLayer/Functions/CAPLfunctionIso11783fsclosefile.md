[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783fsclosefile.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783FSCloseFile

# Iso11783FSCloseFile

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783FSCloseFile( dword fileHandle );
```

## Description

This function closes an opened file or directory.

## Parameters

- **fileHandle**: Handle of the file or directory, which was opened with [Iso11783FSOpenFile](CAPLfunctionIso11783FSOpenFile.md).

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
// handle references a file
LONG handle;
char data[200];

handle = Iso11783FSOpenFile( "\test.TXT", 0x00 );
if (handle > 0) {
  Iso11783FSReadFile( handle, elCount(data), data );
  Iso11783FSCloseFile( handle );
}

// handle references a directory
LONG dirHandle;
char data[200];

dirHandle = Iso11783FSOpenFile( "\dir1", 0x03 );
if (dirHandle > 0) {
  Iso11783FSReadFile( dirHandle, (elCount(data)-2)/22, data);
  Iso11783FSCloseFile( dirHandle );
}
```
