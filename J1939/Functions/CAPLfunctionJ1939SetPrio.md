# J1939SetPrio

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void J1939SetPrio (pg* aPG, dword priority);
```

## Description

Sets the [priority](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group or CAN ID.

## Parameters

- **aPG**: Priority of this parameter group is set.
- **priority**: New priority. A value bigger than 7 is truncated.

## Return Values

—

## Example

See [J1939GetSourceAddress](CAPLfunctionJ1939GetSourceAddress.md).

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)
