[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenInternalNMTCommand.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenInternalNMTCommand

# CANopenInternalNMTCommand

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```c
void CANopenInternalNMTCommand(dword nodeId, dword NMTCommand);
```

## Description

Performs an NMT command inside a simulated CANopen node.

## Parameters

- **nodeID**: ID of the simulated CANopen node.
- **NMTCommand**: Value of the NMT command to be executed:
  - 0x01: Start node
  - 0x02: Stop node
  - 0x80: Enter pre-operational
  - 0x81: Reset node
  - 0x82: Reset communication

## Return Values

The data as qword.

## Example

```c
CANopenInternalNMTCommand(2, 1); // Start node 2
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)