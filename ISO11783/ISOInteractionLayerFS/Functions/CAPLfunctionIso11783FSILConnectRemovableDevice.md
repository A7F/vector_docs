[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILConnectRemovableDevice.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_ConnectRemovableDevice

# FSIL_ConnectRemovableDevice

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_ConnectRemovableDevice(char volumeName[], char pathOfWindowsFolder[], byte maxTimeForRemoval); // form 1
long FSIL_ConnectRemovableDevice(dbNode* fs, char volumeName[], char pathOfWindowsFolder[], byte maxTimeForRemoval); // form 2
```

## Description

Connects a virtual removable device to the File Server.

A common application is to connect a removable device (e.g. a USB stick) to the File Server. With this function you can define a Windows folder which is used by the File Server IL as a virtual removable device.

As a result of the function call, the File Server sends a Volume Status Response with the name of the volume (parameter **volumeName**), maximum time for removal (parameter **maxTimeForRemoval**) and with volume status **Present** to all clients.

If there is no other removable volume available (either a physical media, e.g. a USB stick, or a virtual removable device) and no primary volume is set by [FSIL_SetNodeProperty](CAPLfunctionIso11783FSILSetNodeProperty.md) then the first virtual removable device is used as a primary volume.

You can disconnect the removable device with [FSIL_DisconnectRemovableDevice](CAPLfunctionIso11783FSILDisconnectRemovableDevice.md).

## Parameters

- **volumeName**: Name of the removable volume (without leading "\\").
- **pathOfWindowsFolder**: Path to the Windows folder that is used as a removable virtual disk. Path has to be absolute or relative relating to the folder of the CANoe configuration. Path shall be no subfolder of the root directory. The folder is created if it does not already exist.
- **maxTimeForRemoval**: Maximum time a volume can be held off from being removed [s], 0..255.
- **fs**: FS simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully.
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
// use folder ‘MyRemovableDevices\Device1’
// Path is relative to the folder of the CANoe configuration
FSIL_ConnectRemovableDevice("VOL_A", "MyRemovableDevices\\Device1", 10);
…
// now a File Server client can access files via the volume name e.g.  "\\VOL_A\MyFile.txt"
…
// disconnect removable file File Server is not busy
result = FSIL_DisconnectRemovableDevice("\\VOL_A", 0);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)