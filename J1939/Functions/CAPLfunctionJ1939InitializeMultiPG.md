# J1939InitializeMultiPG

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `J1939InitializeMultiPG(message* multiPG, byte sa); // (form 1)`
- `J1939InitializeMultiPG(message* multiPG, byte prio, byte da, byte sa); // (form 2)`

## Description

Sets CAN ID of the **multiPG** (11 bit CAN ID for form 1 resp. 29 bit for form 2). Form 2 sets the PGN to 0x2500.

- Sets selector FDF of the **multiPG** to 1 (corresponds to CAN FD).
- Sets DLC of the **multiPG** to 4 (minimum length of the **multiPG**).
- The payload of the **multiPG** is assigned with the padding service: the first three bytes are set to 0x00, the last byte to 0xAA.

To add C-PGs to the newly initialized Multi-PG you can use the CAPL function [J1939AddContainedPG](CAPLfunctionJ1939AddContainedPG.md).

## Parameters

- **multiPG**: This message object is to be initiated to **multiPG**.
- **sa**: Source Address of the **multiPG**.
- **da**: Destination Address of the **multiPG**.
- **prio**: Priority of the **multiPG**.

## Return Values

- **0**: **multiPG** is successfully initiated
- **< 0**: an error occurred

## Example

```c
// Here a 11 bit CAN FD message is initialized as multiPG for the source address 0x23:
message* myMultiPG;
J1939InitializeMultiPG(myMultiPG, 0x23);

// Here a 29 bit CAN FD message is initialized as multiPG for the source address 0x23, destination address 0x45 and prio 6:
message* myMultiPG;
J1939InitializeMultiPG(myMultiPG, 6, 0x45, 0x23);
```
