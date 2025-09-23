# J1939GetNumberOfContainedPGs

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939GetNumberOfContainedPGs(message multiPG);
```

## Description

Returns the number of C-PGs which are contained in a [J1939-22 Multi-PG](../../../CANoeCANalyzer/J1939/J1939CANfd/1939CANfd.md). A Padding C-PG (TOS = 0) is ignored.

## Parameters

- **multiPG**: A J1939-22 Multi-PG message

## Return Values

- **≥0**: Number of Contained-PGs which are contained in the message
- **-1**: Message is no J1939-22 Multi-PG message

## Example

```plaintext
on message *
{
  long numOfCpgs, index, result;
  dword pgDataLength, assuranceDataLength;
  byte data[60];
  qword assuranceData;
  pg* cpg;

  if(this.FDF == 0)
  {
    return; //Not a CAN FD message => not a Multi-PG
  }
  numOfCpgs = J1939GetNumberOfContainedPGs(this);
  if(numOfCpgs <= 0)
  {
    return;
  }
  for (index=0; index<numOfCpgs; index++)
  {
    result = J1939GetContainedPG(this, index, cpg);
    if (result < 0)
    {
      writeEx(-3, 3, "J1939GetContainedPG for index %i failed with error %i", index, result);
      continue;
    }
    //Get PG data only
    pgDataLength = J1939GetContainedPGData(this, index, data);
    //Get assurance data only
    assuranceDataLength = J1939GetContainedPGAssuranceData(this, index, assuranceData);

    writeEx(-3, 0, "%i. C-PG (PGN 0x%X, tos %u, tf %u): %u byte payload, %u PG data, %u assurance data",
      index+1, cpg.pgn, cpg.tos, cpg.tf, cpg.dlc, pgDataLength, assuranceDataLength);
  }
}
```
