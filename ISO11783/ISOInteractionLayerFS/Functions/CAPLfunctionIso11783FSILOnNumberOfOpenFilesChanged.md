[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILOnNumberOfOpenFilesChanged.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_OnNumberOfOpenFilesChanged**

# FSIL_OnNumberOfOpenFilesChanged (Callback)

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
void FSIL_OnNumberOfOpenFilesChanged( dword clientAddress, dword numberOfOpenFiles)
```

## Description

Is called from the FS IL if a client has opened or closed a file or directory.

## Parameters

- **clientAddress**: Address of the File Server client which has opened or closed a file or directory.
- **numberOfOpenFiles**: Current number of files or directories which are opened by the File Server client.

## Return Values

—

## Example

```plaintext
void FSIL_OnNumberOfOpenFilesChanged( dword clientAddress, dword numberOfOpenFiles)
{
  write("Client with address %u has %u open files", clientAddress, numberOfOpenFiles);
}
```
