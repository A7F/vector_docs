[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILDisconnectRemovableDevice.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_DisconnectRemovableDevice

# FSIL_DisconnectRemovableDevice

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_DisconnectRemovableDevice(char volumeName[], dword flags); // form 1
long FSIL_DisconnectRemovableDevice(dbNode* fs, char volumeName[], dword flags); // form 2
```

## Description

Disconnects a virtual or physical removable device from the File Server that was previously connected by [FSIL_ConnectRemovableDevice](CAPLfunctionIso11783FSILConnectRemovableDevice.md) or plugged in.

Depending on the parameter **flags**, the volume is removed at once or File Server sends a notification to the clients before the volume is removed.

If the disconnected volume was the primary volume, then the next removable device is used as primary volume. If there is no other removable volume, then no primary volume is set.

After a virtual device is disconnected, the appropriate Windows folder is still available.

## Parameters

- **volumeName**: Name of the removable volume (without leading "\\").
- **flags**:
  - **Bit 0 = 0**: Removes volume at once and sends a Volume Status Response with the name of the volume (parameter **volumeName**) and with volume status **Removed** to all clients.
  - **Bit 0 = 1**: First sends a Volume Status Response with the name of the removable volume (parameter **volumeName**) and with volume status **Preparing for removal** to all clients. If within 2 seconds there are no more Volume Status Request with value **In Use** from a client or if the maximum time for removal is expired, then the File Server sends a Volume Status Response with volume status **Removed** and removes the volume.
- **fs**: FS simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully.
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

See: [FSIL_ConnectRemovableDevice](CAPLfunctionIso11783FSILConnectRemovableDevice.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)