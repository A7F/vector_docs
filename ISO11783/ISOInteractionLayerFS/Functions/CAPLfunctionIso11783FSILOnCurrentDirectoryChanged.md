[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILOnCurrentDirectoryChanged.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_OnCurrentDirectoryChanged

# FSIL_OnCurrentDirectoryChanged (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void FSIL_OnCurrentDirectoryChanged( dword clientAddress, char currentDirectory[]);
```

## Description

Is called from the FS IL if a client has changed its current directory.

## Parameters

- **clientAddress**: Address of the File Server client which has changed its current directory.
- **currentDirectory**: Path of the current directory (relative to the root directory).

## Return Values

—

## Example

```plaintext
void FSIL_OnCurrentDirectoryChanged( dword clientAddress, char currentDirectory[])
{
  write("Client with address %u has changed it current directory to '%s'", clientAddress, currentDirectory);
}
```
