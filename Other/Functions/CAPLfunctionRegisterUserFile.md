# RegisterUserFile

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long RegisterUserFile(char userFilePath[], long isTemporaryRegistration);
```

## Description

Registers [user files](../../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md) dynamically.

This function can be used:

- If files names are not known before runtime (e.g., if they are read out from an XML file or if they contain a counter as part of the filename).
- To avoid the continuous actualization of the file list in the [Options](../../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md) dialog of CANoe DE product.

## Parameters

- **userFilePath**: Absolute or relative (to the configuration directory) path of the user file's storage location on the user computer.
- **isTemporaryRegistration**: If set to 0, the registered file will be added permanently to the User Files list of the current CANoe DE product configuration; if set to 1, the registration is only valid for the current measurement run.

## Return Values

- **1**: File successfully registered
- **-1**: File registration failed

## Example

—

[getUserFilePath](CAPLfunctionGetUserFilePath.md)
