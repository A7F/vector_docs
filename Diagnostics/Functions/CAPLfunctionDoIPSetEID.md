# DoIP_SetEID, DoIP_SetGroupIdentification, DoIP_SetVIN

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetEID(byte EID[]);
void DoIP_SetGroupIdentification(byte GID[], dword furtherActionRequired, dword VINGIDsyncStatus);
void DoIP_SetVIN(byte VIN[]);
void DoIP_SetVIN(char VIN[]);
```

## Description

Configures the Vehicle Announcement/Vehicle Identification Response Message sent by a vehicle simulation.

**Note**  
If these functions are used in combination with [DiagInitEcuSimulation](../../KLine/Functions/CAPLfunctionDiagInitEcuSimulation.md), the functions must be called in [on prestart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md). Otherwise the functions have no effect.

Reason: The DoIP.DLL is initialized in a ECU simulation **after** on prestart but **before** on start.

## Parameters

- **EID**: Send this entity ID in the message, e.g. a MAC address.
- **GID**: Send this group identity in the message, e.g. a MAC address.
- **furtherActionRequired**: 0: No further action is required (default)
- **VINGIDsyncStatus**: 0: VIN and GID are synchronized (default)  
  0x10: VIN and GID are NOT synchronized; the tester should repeat the Vehicle Identification Request.
- **VIN**: Vehicle Identification Number sent in the message.

## Return Values

—

## Example

These values can also be configured in the DoIP.INI file.

```plaintext
// Set the entity and group IDs
BYTE eid[6] = { 0x20, 0x11, 0x22, 0x33, 0x44, 0x55};
BYTE gid[6] = { 0x20, 0x11, 0x22, 0x33, 0xFF, 0xFF};
DoIP_SetEID( eid);
// Indicate that VIN and GID are not synchronized yet, i.e. the tester shall repeat
// the Vehicle Identification Request after some time
DoIP_SetGroupIdentification( gid, 0, 0x10);
if( gSetVINasBytes)
{
  // Alternatively, set the VIN using a raw byte stream
  BYTE rawVIN[17] = { 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF };
  DoIP_SetVIN( rawVIN);
} else
{
  // Set the VIN using its textual representation
  DoIP_SetVIN("VECT0RVEH1CLE1234");
}
```
