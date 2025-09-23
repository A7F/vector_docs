# J1939GetPGN

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

- `dword J1939GetPGN (pg* aPG); // form 1`
- `dword J1939GetPGN (dword canId); // form 2`

## Description

Returns the [parameter group number (PGN)](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group or CAN ID.

## Parameters

- **aPG**: The function returns the PGN of this parameter group.
- **canId**: The function returns the PGN of this CAN ID.

## Return Values

- **0..3FFFFh**: Parameter group number.

## Example

See [J1939GetSourceAddress](CAPLfunctionJ1939GetSourceAddress.md).

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)
