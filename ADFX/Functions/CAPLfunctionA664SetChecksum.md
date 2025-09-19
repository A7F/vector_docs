# A664SetChecksum

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long A664SetChecksum (a664Frame aFrame, dword Rule)
```

## Description

This function calculates and sets the checksum in the specified `aFrame` according to the defined checksum rule.

## Parameters

- **aFrame**: The [a664Frame](../../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXframe.md) object where the checksum is calculated and stored.
- **Rule**: Defines the checksum rule based on the protocol type.
  - 1 – IP checksum
  - 2 – ICMP checksum
  - 3 – UDP checksum

## Return Values

- `<success>`: Calculated checksum value –› all values including 0.
- `<error> -1`: Invalid `Rule`.
- `<error> -2`: Packet protocol type inconsistent with rule type.

## Example

—
