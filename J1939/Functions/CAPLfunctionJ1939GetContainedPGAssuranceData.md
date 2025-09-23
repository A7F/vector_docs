# J1939GetContainedPGAssuranceData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long J1939GetContainedPGAssuranceData(message multiPG, byte index, qword assuranceData);
```

## Description

Returns the assurance data of a Contained-PG (C-PG) at the specified index of a [J1939-22 Multi-PG](../../../CANoeCANalyzer/J1939/J1939CANfd/1939CANfd.md).

## Parameters

- **multiPG**: A J1939-22 Multi-PG message
- **index**: Index of the C-PG within the Multi-PG
- **assuranceData**: Returns the assurance data of the C-PG

## Return Values

- **>0**: Length in bytes of assurance data
- **0**: C-PG contains no assurance data
- **-1**: Message is no J1939-22 Multi-PG message
- **-2**: Index is invalid

## Example

See [J1939GetNumberOfContainedPGs](CAPLfunctionJ1939GetNumberOfContainedPGs.md).
