[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783fsgetfileinfo.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783FSGetFileInfo

# Iso11783FSGetFileInfo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783FSGetFileInfo( dword fileHandle, dword infoCount, dword retInfo[] );
long Iso11783FSGetFileInfo( char fileName[], dword infoCount, dword retInfo[] );
```

## Description

This function retrieves information about a file or directory. In the entry of the array, the following information is returned:

- **Index 0**: bit-field with valid entries, bit 1 set = index 1 is valid, ...
- **Index 1**: attributes of the file:
  - Bit 1: Read Only
  - Bit 2: Hidden
  - Bit 3: System
  - Bit 5: Directory
  - Bit 6: Archive
  - Bit 7: File/Directory is on removable media
- **Index 2**: year
- **Index 3**: month
- **Index 4**: day
- **Index 5**: hour
- **Index 6**: minute
- **Index 7**: second

## Parameters

- **fileHandle**: File or directory handle, see also [Iso11783FSOpenFile](CAPLfunctionIso11783FSOpenFile.md)
- **fileName**: Name of file or directory
- **infoCount**: Number of elements in `retInfo`
- **retInfo**: Contains the information about the file or directory

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
LONG handle;
dword info[8];

handle = Iso11783FSOpenFile( "\TEST.TXT", 0x00 );
if (handle > 0) {
    if (Iso11783FSGetFileInfo( handle, elCount(info), info ) == 0) {
        write( "Date %d-%d-%d'", info[2], info[3], info[4] );
    }
    Iso11783FSCloseFile( handle );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
