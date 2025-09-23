# J1939GetContainedPGData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939GetContainedPGData(message multiPG, byte index, byte[] data);
```

## Description

Returns the PG Data of a Contained PG (C-PG) at the specified index of a [J1939-22 Multi-PG](../../../CANoeCANalyzer/J1939/J1939CANfd/1939CANfd.md).

The maximum length of PG Data is 60 bytes.

## Parameters

- **multiPG**: A J1939-22 Multi-PG message
- **index**: Index of the C-PG within the Multi-PG
- **payload**: Returns the PG Data of the C-PG

## Return Values

- **≥0**: Length in bytes of PG Data
- **-1**: Message is no J1939-22 Multi-PG message
- **-2**: Index is invalid

## Example

See [J1939GetNumberOfContainedPGs](CAPLfunctionJ1939GetNumberOfContainedPGs.md).
