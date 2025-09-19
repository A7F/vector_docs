[J1939ILGetDeviceName](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILGetDeviceName.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILGetDeviceName

# J1939ILGetDeviceName

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILGetDeviceName(qword& deviceName); // form 1`
- `long J1939ILGetDeviceName(byte[] deviceName); // form 2`
- `long J1939ILGetDeviceName(dbNode node, qword& deviceName); // form 3`
- `long J1939ILGetDeviceName(dbNode node, byte[] deviceName); // form 4`

## Description

Function returns the current J1939 NAME of the simulation node (as set in the database and possibly changed by [J1939ILSetNodeProperty](CAPLfunctionJ1939ILSetNodeProperty.md)).

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
  J1939ILGetDeviceName(deviceName);
  write("DeviceName: 0x%Xll", deviceName);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
