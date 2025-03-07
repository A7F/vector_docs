[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783fsmove.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » **Iso11783FSMove**

# Iso11783FSMove

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783FSMove( char sourcePath[], char destPath[], dword movemode );
```

## Description

The function moves, copies or deletes a file or directory.

## Parameters

- **sourcePath**: Absolute file or directory source path
- **destPath**: Absolute file or directory destination path or 0 to delete the file or directory specified in `sourcePath`
- **movemode**:
  - **Bit 0**: 
    - Value: 0 - Action: copy
    - Value: 1 - Action: move
  - **Bit 1**: 
    - Value: 1 - delete option: force
  - **Bit 2**: 
    - Value: 1 - delete option: recursive

The two delete options "recursive" and "force" only have an impact on the deletion process. In this context, recursive means the deletion of a directory with its content, whereas "force" enables a read-only file or directory to be deleted.

To rename a file, specify the new path and name in `destPath`. Renaming a file or directory can be combined with moving or copying it to a new location.

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
// Move
Iso11783FSMove( "\TEST.TXT", "\DIR1\TEST.TXT", 0x00 );

// Copy & Rename
Iso11783FSMove( "\TEST.TXT", "\DIR1\TEST2.TXT", 0x01 );

// Delete (even, if "TEST.TXT" is read-only)
Iso11783FSMove( "\TEST.TXT", 0, 0x06 );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)