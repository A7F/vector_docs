[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783fssetfileinfo.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783FSSetFileInfo

# Iso11783FSSetFileInfo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783FSSetFileInfo( dword fileHandle, dword infoCount, dword info[] );
long Iso11783FSSetFileInfo( char fileName[], dword infoCount, dword info[] );
```

## Description

This function sets file or directory attributes.

## Parameters

- **fileHandle**: File or directory handle, see also [Iso11783FSOpenFile](CAPLfunctionIso11783FSOpenFile.md)
- **fileName**: Name of file or directory
- **infoCount**: Number of elements in `info`
- **info**: Array containing the attributes to set

  - **Index 0**: bit field with valid elements, Bit 1 set = Index 1 is valid, ...
  - **Index 1**: attributes to be set:
    - **Bit 1-2**: Read-only attribute
      - 0: Clear
      - 1: Set
      - 3: No change
    - **Bit 3-4**: Hidden attribute
      - 0: Clear
      - 1: Set
      - 3: No change
    - **Bit 5-6**: System attribute
      - 0: Clear
      - 1: Set
      - 3: No change
    - **Bit 7-8**: Archive attribute
      - 0: Clear
      - 1: Set
      - 3: No change

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
LONG handle;
dword info[2];

handle = Iso11783FSSetFileInfo( "\TEST.TXT", 0x00 );
if (handle > 0) {
  info[0] = 0x01; // Entry 1 is valid
  info[1] = 0x04; // Hide file
  if (Iso11783FSSetFileInfo( handle, elCount(info), info ) == 0) {
    write( "Changed attributes successfully" );
  }
  Iso11783FSCloseFile( handle );
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
