[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILGetDeviceName.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_GetDeviceName**

# Iso11783IL_GetDeviceName

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_GetDeviceName(qword& deviceName); // form 1`
- `long Iso11783IL_GetDeviceName(byte[] deviceName); // form 2`
- `long Iso11783IL_GetDeviceName(dbNode node, qword& deviceName); // form 3`
- `long Iso11783IL_GetDeviceName(dbNode node, byte[] deviceName); // form 4`

## Description

Function returns the current J1939 NAME of the simulation node (as set in the database and possibly changed by [Iso11783IL_SetNodeProperty](CAPLfunctionIso11783ILSetNodeProperty.md)).

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
  Iso11783IL_GetDeviceName(deviceName);
  write("DeviceName: 0x%Xll", deviceName);
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)