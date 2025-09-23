[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILImportFiles.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_ImportFiles

# FSIL_ImportFiles

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_ImportFiles( char targetPath[], char sourcePath[]); // form 1`
- `long FSIL_ImportFiles( dbNode fs, char targetPath[], char sourcePath[]); // form 2`

## Description

Imports files into the File Server.

Adds a file or the content of a local directory to the File Server. Existing directories and files are replaced if they are not write protected.

## Parameters

- **fs**: FS simulation node to apply the function
- **targetPath**:
  - Files are copied into this path. The path is relative to the root directory of the File Server.
  - If the path is an empty string then the files are copied into root directory of the File Server.
  - If the directory does not exist then it is created.
- **sourcePath**:
  - Path of a file or a directory which contains files and directories. Path has to be absolute or relative relating to the folder of the CANoe configuration.
  - This file or the content of this directory is copied into the File Server. Thus, you can create a predefined environment for File Server clients.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
FSIL_ImportFiles("Volume1\MSM1861\VT1", "VT1_Pools");

FSIL_ImportFiles("Volume1\MSM1861\VT1", "VT1_Pools\2FB3AAE801840CA0_SprayV0.iop");

FSIL_ImportFiles("", "Volume1\MSM1861\VT1\VT1_Pools");
```
