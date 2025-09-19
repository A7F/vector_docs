[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783fsmakeabsolutepath.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » **Iso11783FSMakeAbsolutePath**

# Iso11783FSMakeAbsolutePath

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783FSMakeAbsolutePath( char relPath[], char absPath[], dword mustExist, dword bufferSize, char buffer[] );
long Iso11783FSMakeAbsolutePath( char relPath[], char absPath[], dword mustExist, dword bufferSize, char buffer[], char volume[], long manufacturerCode );
```

## Description

This function converts a relative path into an absolute path including a conversion to uppercase characters. An absolute path begins with `\` and refers to the root directory (see also [Iso11783SetPath](CAPLfunctionIso11783fssetpath.md)). A relative path could contain `..` and `.`.

A path must follow the 8.3 format (8 character identifier with 4 character extension).

## Parameters

- **relPath**: Relative path which could contain `..` and `.`.
- **absPath**: Absolute path.
- **mustExist**:
  - 1: check if path exists and return an error if the file does not exist.
  - 0: the path must not exist.
- **bufferSize**: Size of `buffer` in byte.
- **buffer**: New path is copied to this buffer.
- **volume**: Name of the volume, this information and the manufacturer code are needed to resolve the root directory in the paths.
- **manufacturerCode**: Manufacturer code, this information and the volume are needed to resolve the root directory in the paths.

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
char defaultDirectory[64] = "\IMPL";
char newPath[255];

if (Iso11783FSMakeAbsolutePath( "..\DATA", defaultDirectory, 1, elCount(newPath), newPath ) == 0) {
  write( "Path '%s'", newPath );
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
