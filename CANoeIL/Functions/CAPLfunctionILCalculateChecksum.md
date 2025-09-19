# ILCalculateChecksum

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILCalculateChecksum (char pduNamme[], long type, BYTE payload[], long payloadLength, BYTE crc [])
```

## Description

Calculates the corresponding CRC checksum based on the payload. The correct offset is calculated from the database using the PDU name.

## Parameters

- **pduName**: Name of the PDU.
- **type**: 
  - type = 0 : CRC
  - type = 1 : CHK
- **payload**: Payload for which the checksum is to be calculated.
- **payloadLength**: Number of data bytes in payload.
- **crc**: The calculated checksum.

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

—

[TestFRILCalculateChecksum](../../Test/Functions/CAPLfunctionTestFRILCalculateChecksum.md)
