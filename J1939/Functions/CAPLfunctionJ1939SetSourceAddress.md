# J1939SetSourceAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void J1939SetSourceAddress (pg* aPG, dword sourceAddress);
```

## Description

Sets the [source address](../../../CANoeCANalyzer/J1939/j1939basics/j1939PGandPGN.md) of a parameter group.

## Parameters

- **aPG**: Source address of this parameter group is set.
- **sourceAddress**: New source address. A value bigger than 255 is truncated.

## Return Values

—

## Example

—

[J1939 General Functions](../CAPLfunctionsJ1939Overview.md#General)
