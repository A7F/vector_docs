# J1939ParseSHM

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long J1939ParseSHM(pg* pgSHM, dword & sdmPgn, byte& sdmSourceAddress, byte& sdmDestinationAddress, byte& sequenceNumber, dword & crc):
```

## Description

Provides data of the SDM message, which are contained in payload of the SHM message according to [SAE J1939-76](../../../CANoeCANalyzer/J1939/j1939basics/j1939FunctionalSafety.md).

## Parameters

- **pgSHM**: SHM to parse. DLC of SHM shall be 8.
- **sdmPgn**: Returns the PGN of the SDM.
- **sdmSourceAddress**: Returns the source address of the SDM.
- **sdmDestinationAddress**: Returns the destination address of the SDM.
- **sequenceNumber**: Returns the sequence number of the Safety Data Group (SDG).
- **crc**: Returns the SDM Data CRC.

## Return Values

- **0**: SHM is successfully parsed.
- **-1**: DLC of a PG is not 8 bytes.

## Example

```plaintext
on pg SHM
{
  long result;
  dword sdmPgn, crc;
  byte sdmSourceAddress, sdmDestinationAddress, sequenceNumber;

  result = J1939ParseSHM(this, sdmPgn, sdmSourceAddress, sdmDestinationAddress, sequenceNumber, crc);
  if (result < 0)
  {
    write("J1939ILParseSHM failed with error %i", result);
  }
  else
  {
    if ((sdmPgn == pgnOfConsumedMsg)
        && (sdmDestinationAddress == saOfConsumedMsg)
        && (sdmSourceAddress == daOfConsumedMsg))
    {
      // validate sequence number of SHM and store store CRC to validate it when SDM is received
    }
  }
}
```

[J1939CalculateCrcOfSDM](CAPLfunctionJ1939CalculateCrcOfSDM.md) • [J1939ParseSHM](#)
