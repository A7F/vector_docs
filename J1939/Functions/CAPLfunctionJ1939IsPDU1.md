# J1939IsPDU1

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939IsPDU1 (dword canId);
```

## Description

Checks if the parameter group number (PGN) contained in the CAN ID has the [PDU Format 1](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md).

## Parameters

- **canId**: CAN ID to check.

## Return Values

- **0**: PGN is PDU Format 2.
- **1**: PGN is PDU Format 1.

## Example

—

[J1939IsPDU2](CAPLfunctionJ1939IsPDU2.md)
