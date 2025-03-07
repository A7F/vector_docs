[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILSetBusyMode.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_SetBusyMode**

# FSIL_SetBusyMode

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_SetBusyMode(byte flags); // form 1`
- `long FSIL_SetBusyMode(dbNode* fs, byte flags); // form 2`

## Description

Activates or deactivates the busy mode of the File Server.

If at least one of the busy mode flags is set:

- File Server Status message is sent with a repetition rate of 200 ms.
- Busy flag of the File Server Status is changed.

Even busy mode is set the File Server responds to requests of a client.

## Parameters

- **flags**
  - bit 0: File Server is busy reading
  - bit 1: File Server is busy writing

- **fs**
  - FS simulation node to apply the function

## Return Values

- **0**
  - Property has been set successfully

- **< 0**
  - An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example (applicable only in a test node)

```plaintext
//Set File Server for 5 sec in a busy mode
FSIL_SetBusyMode(FileServer, 0x2) // File Server is busy writing
testWaitForTimeout(5000);  // Wait for 5000 ms
FSIL_SetBusyMode(FileServer, 0) // File Server is not busy
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)