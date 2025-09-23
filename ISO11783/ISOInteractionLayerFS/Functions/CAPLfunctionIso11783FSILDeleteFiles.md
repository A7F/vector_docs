[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILDeleteFiles.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_DeleteFiles

# FSIL_DeleteFiles

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_DeleteFiles( char path[], byte options); // form 1`
- `long FSIL_DeleteFiles( dbNode fs, char path[], byte options); // form 2`

## Description

Deletes a file or directory of the File Server.

## Parameters

- **fs**: FS simulation node to apply the function
- **path**:
  - Path of a file or directory to delete. The path is absolute or relative to the root directory of the File Server.
  - If the path is an empty string then all directories and files of the root directory are deleted.
- **options**:
  - Bit 0 = 0: The specified file or directory is deleted
  - Bit 0 = 1: Only the content of the specified directory is deleted (this value is only valid if parameter path is a directory)

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
