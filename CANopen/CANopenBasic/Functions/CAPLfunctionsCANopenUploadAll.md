[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenUploadAll.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenUploadAll

# CANopenUploadAll

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
void CANopenUploadAll (dword serverNodeID, dword blockMode, dword[] errCode);
```

## Callback

```plaintext
OnCANopenUploadAllResponse(dword nodeID)
```

## Description

Reads all objects from the object dictionary of another node. The callback is called after all entries are read and the corresponding system variables are updated.

## Parameters

- **serverNodeID**: Node ID of the SDO server.
- **blockMode**: 
  - **0**: Do not use SDO block transfer.
  - **1**: Use SDO block transfer.
- **errCode**: Error code buffer (is entered in index 0 of the field):
  - **0**: Operation can be started.
  - **1**: Operation already running.
  - **5**: No CANopen license.
  - **6**: No CAN channel.

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)