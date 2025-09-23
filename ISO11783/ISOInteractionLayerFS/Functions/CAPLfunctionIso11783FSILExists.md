[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILExists.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_Exists

# FSIL_Exists

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_Exists( char path[]); // form 1
long FSIL_Exists( dbNode fs, char path[]); // form 2
```

## Description

Checks if a file or directory does exist.

## Parameters

- **fs**: FS simulation node to apply the function
- **path**: Path of a file or directory. The path is absolute or relative to the root directory of the File Server.

## Return Values

- **1**: File exits
- **0**: File or directory does not exist
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
