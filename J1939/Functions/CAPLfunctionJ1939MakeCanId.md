# J1939MakeCanId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939MakeCanId (byte priority, dword pgn, byte destinationAddress, byte sourceAddress, byte setExtendedBit);
```

## Description

Assembles a CAN ID of a [parameter group](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) (PG) from source/destination address, parameter group number (PGN) and priority.

For a PGN of PDU Format 2, the parameter destination address is ignored.

The parameter **setExtendedBit** defines whether the most significant bit of the resulting CAN ID is set (see [CAN Extended Identifier](../../../CANoeCANalyzer/General/CANExtendedIdentifier.md)).

## Parameters

- **priority**: Priority of the PG.
- **pgn**: Parameter group number (PGN) of the PG.
- **destinationAddress**: Destination address of the PG.
- **sourceAddress**: Source address of the PG.
- **setExtendedBit**: Defines whether the most significant bit of the resulting CAN ID is set.

## Return Values

—

## Example

—

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)
