# J1939GetDataPage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword J1939GetDataPage (Node aNode); // form 1`
- `dword J1939GetDataPage (dword canId); // form 2`

## Description

Returns the [data page](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) bit of a parameter group or CAN ID.

## Parameters

- **aPG**: The function returns the data page of this parameter group.
- **canId**: The function returns the data page of this CAN ID.

## Return Values

- **0 or 1**: Data page bit.

## Example

See [J1939GetSourceAddress](CAPLfunctionJ1939GetSourceAddress.md).

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)
