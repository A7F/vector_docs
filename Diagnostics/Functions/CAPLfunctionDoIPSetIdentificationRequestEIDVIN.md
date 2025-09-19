# DoIP_SetIdentificationRequestEID, DoIP_SetIdentificationRequestVIN

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetIdentificationRequestEID(byte EID[]);
void DoIP_SetIdentificationRequestVIN(char VIN[]);
```

## Description

Configures the Vehicle Identification Request Message sent by a tester.

## Parameters

- **EID**: Send an entity ID in the message, e.g. a MAC address.
- **VIN**: Send a Vehicle Identification Number in the message. If this is an empty string, the message will be sent without indicating a specific vehicle.

## Return Values

—

## Example

The message can also be configured from the DoIP.INI file.

```plaintext
// Send the MAC address 20:11:22:33:44:55 in the VIR message
BYTE eid[6] = { 0x20, 0x11, 0x22, 0x33, 0x44, 0x55};
DoIP_SetIdentificationRequestEID( eid);

// Send a VIN in the VIR message
DoIP_SetIdentificationRequestVIN( "VECT0RVEH1CLE1234");

// Do not address a specific vehicle, i.e. all vehicles shall respond
DoIP_SetIdentificationRequestVIN( "");
```
