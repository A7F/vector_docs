# J1939GetPrio

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword J1939GetPrio (pg* aPG); // form 1`
- `dword J1939GetPrio (dword canId); // form 2`

## Description

Returns the J1939 [priority](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group or CAN ID.

## Parameters

- **aPG**: The function returns the priority of this parameter group.
- **canId**: The function returns the priority of this CAN ID.

## Return Values

- **0..7**: Priority

## Example

See [J1939GetSourceAddress](CAPLfunctionJ1939GetSourceAddress.md).

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)
