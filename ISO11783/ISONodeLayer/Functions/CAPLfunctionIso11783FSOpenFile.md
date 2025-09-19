[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783FSOpenFile.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » iso11783FSOpenFile

# iso11783FSOpenFile

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long iso11783FSOpenFile( char path[], dword flags );
```

## Description

This function opens a file or directory.

## Parameters

- **path**: absolute path of the file
- **flags**: options to open the file
  - **Bit 1-2**
    - 0: Read only
    - 1: Write only
    - 2: Read and write
    - 3: Open directory for reading
  - **Bit 3**
    - 0: Open an existing file or directory
    - 1: Create a new file or directory if not yet existing
  - **Bit 4**
    - 0: Random access
    - 1: Append
  - **Bit 5**
    - 0: Shared access
    - 1: Exclusive access

## Return Values

- **> 0**: file handle
- **< 0**: [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
LONG handle;
char data[200];

handle = iso11783FSOpenFile("\test.TXT", 0x00);
if (handle > 0) {
  Iso11783FSReadData(handle, elCount(data), data);
  Iso11783FSCloseFile(handle);
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
