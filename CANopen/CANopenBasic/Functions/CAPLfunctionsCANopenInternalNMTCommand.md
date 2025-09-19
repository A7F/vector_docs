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
