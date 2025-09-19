[J1939GetDeviceName](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939GetDeviceName.md)

**CAPL Functions** » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939GetDeviceName

# J1939GetDeviceName

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939GetDeviceName(byte address, qword& deviceName); // (form 1)`
- `long J1939GetDeviceName(byte address, byte[] deviceName); // (form 2)`
- `long J1939GetDeviceName(dbNode node, qword& deviceName); // (form 3)`
- `long J1939GetDeviceName(dbNode node, byte[] deviceName); // (form 4)`

## Description

Function retrieves the J1939 NAME for a J1939 node - as reported on the bus with the PG **Address Claimed**. However, if the node is offline or did not report its name, the function retrieves the J1939 NAME from the database if available.

## Parameters

- **address**: Address of the J1939 node whose J1939 NAME is to be retrieved.
- **node**: Database node that identifies the J1939 node whose J1939 NAME is to be retrieved.
- **deviceName (forms 1 and 3)**: Retrieved J1939 NAME as a qword.
- **deviceName (forms 2 and 4)**: Retrieved J1939 NAME as a byte array with at least 8 bytes length.

## Return Values

- **0**: Success, node is offline.
- **1**: Success, node is online.
- **-1**: Device name not available or not seen on the bus.
- **-2**: Array length is less than 8 bytes.

## Example

```plaintext
on key '1'
{
  qword deviceName;
  // Get the J1939 NAME (as a qword) of node with address 0xA
  J1939GetDeviceName(0xA, deviceName);
  write("DeviceName: 0x%Xll", deviceName);
}
```

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
