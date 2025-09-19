[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILGetDeviceName.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_GetDeviceName**

# FSIL_GetDeviceName

[Feature availability for your product](../../../../Shared/FeatureAvailability.md): Valid for CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_GetDeviceName(qword& deviceName); // form 1`
- `long FSIL_GetDeviceName(byte[] deviceName); // form 2`
- `long FSIL_GetDeviceName(dbNode node, qword& deviceName); // form 3`
- `long FSIL_GetDeviceName(dbNode node, byte[] deviceName); // form 4`

## Description

Function returns the current J1939 NAME of the simulation node (as set in the database and possibly changed by [FSIL_SetNodeProperty](CAPLfunctionIso11783FSILSetNodeProperty.md)).

## Parameters

- **deviceName (Forms 1 and 3)**: Retrieved J1939 NAME as a qword.
- **deviceName (Forms 2 and 4)**: Retrieved J1939 NAME as a byte array with at least 8 bytes length.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: Success, node is offline.
- **1**: Success, node is online.
- **-1**: No device name available.
- **-2**: Byte array is less than 8 bytes.

## Example

```plaintext
on key '1'
{
  qword deviceName;
  // Get the J1939 NAME (as a qword) of the current simulation node
  FSIL_GetDeviceName(deviceName);
  write("DeviceName: 0x%Xll", deviceName);
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
