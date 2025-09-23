# J1939FillSHM

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939FillSHM(pg pgSDM, byte sequenceNumber, pg* pgSHM);
```

## Description

This function uses the PGN, addresses, priority and payload of a Safety Data Message (**SDM**) as well as a sequence number to set the payload, priority and addresses of a Safety Header Message (**SHM**).

The payload of the SDM consist of following signals (see [SAE J1939-76](../../../CANoeCANalyzer/J1939/j1939basics/j1939FunctionalSafety.md)):

- Inverted SDM Data Page.
- Inverted SDM Extended Data Page.
- SDG Sequence Number.
- Inverted SDM Source Address.
- Inverted SDM PS Value.
- Inverted SDM PF Value.
- SDM Data CRC.

## Parameters

- **pgSDM**: The data of SDM is used to fill the SHM. DLC of SDM shall be 8.
- **sequenceNumber**: New sequence number of the SHM.
- **pgSHM**: SHM message to be filled. DLC of SHM shall be 8.

## Return Values

- **0**: SHM is successfully filled.
- **-1**: DLC of SDM is not 8 bytes.

## Example

```plaintext
void SendSHM(pg* sdm, byte sequenceNumber)
{
  pg SHM shm;
  long result;
  result = J1939FillSHM(sdm, sequenceNumber, shm);
  if (result < 0)
  {
    write("J1939FillSHM failed with error %i", result);
  }
  else
  {
    output(shm);
  }
}
```

[J1939CalculateCrcOfSDM](CAPLfunctionJ1939CalculateCrcOfSDM.md) • [J1939ParseSHM](CAPLfunctionJ1939ParseSHM.md)
