# J1939CalculateCrcOfSDM

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939CalculateCrcOfSDM(qword sdmPayload)
```

## Description

Calculates CRC for payload of a Safety Data Message according to [SAE J1939-76](../../../CANoeCANalyzer/J1939/j1939basics/j1939FunctionalSafety.md)

## Parameters

- **sdmPayload**: Payload of a Safety Data Message.

## Return Values

Calculated CRC

## Example

—

[J1939FillSHM](CAPLfunctionJ1939FillSHM.md) • [J1939ParseSHM](CAPLfunctionJ1939ParseSHM.md)
