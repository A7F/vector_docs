# J1939GetContainedPG

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long J1939GetContainedPG(message multiPG, byte index, pg cpg);
```

## Description

Returns a Contained PG (C-PG) at the specified index of a [J1939-22 Multi-PG](../../../CANoeCANalyzer/J1939/J1939CANfd/1939CANfd.md).

This function does not return the parameters of Padding C-PG (TOS = 0).

## Parameters

- **multiPG**: A J1939-22 Multi-PG message.
- **index**: Index of the C-PG within the Multi-PG.
- **cpg**: This PG is filled with data of the Contained PG (Parameter Group Number (PGN), type of service, trailer format, payload as well as source and destination address of the Multi-PG and priority of the Multi-PG.

## Return Values

- **0**: The function successfully determined the parameters
- **-1**: Message is not a J1939-22 Multi-PG message
- **-2**: Index is invalid

## Example

See [J1939GetNumberOfContainedPGs](CAPLfunctionJ1939GetNumberOfContainedPGs.md).
