[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILDisconnectAllRemovableDevices.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_DisconnectAllRemovableDevices**

# FSIL_DisconnectAllRemovableDevices

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_DisconnectAllRemovableDevices(dword flags); // form 1
long FSIL_DisconnectAllRemovableDevices(dbNode* fs, dword flags); // form 2
```

## Description

Disconnects all virtual and physical removable devices from the File Server that were previously connected by [FSIL_ConnectRemovableDevice](CAPLfunctionIso11783FSILConnectRemovableDevice.md) or plugged in.

Depending on the parameter **flags**, the volumes are removed at once or File Server sends a notification to the clients before the volume is removed.

If one of the connected volumes was the primary volume then no primary volume is set after the volumes are removed.

After a virtual device is disconnected, the appropriate Windows folder is still available.

## Parameters

- **flags**:
  - **Bit 0 = 0**: Removes all volumes at once and sends a Volume Status Response for every volume with the name of the volume (parameter **volumeName**) and with volume status **Removed** to all clients.
  - **Bit 0 = 1**: For every removable volume: First sends a Volume Status Response with the name of the removable volume (parameter **volumeName**) and with volume status **Preparing for removal** to all clients. If within 2 seconds there are no more Volume Status Request with value **In Use** from a client or if the maximum time for removal is expired then the File Server sends a Volume Status Response with volume status **Removed** and removes the volume.

- **fs**: FS simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully.
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
