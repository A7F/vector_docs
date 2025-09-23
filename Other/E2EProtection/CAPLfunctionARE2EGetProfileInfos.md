# ARE2EGetProfileInfos

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARE2EGetProfileInfos (PDU * aPDU, char sigGroupName[], char aCategory[], long categoryLength, long & aProfile, long & dataIDMode, long & dataOffset , long & dataLength, long & crcOffset, long & counterOffset);
```

## Description

Returns profile information of a PDU with E2E protection. It is necessary that the PDU has a valid E2E.

## Parameters

- **aPDU**: A referenced PDU object.
- **sigGroupName**: The name of the signal group or empty. If empty, then the E2E should be directly defined at the PDU instead of the signal group.
- **aCategory**: A string with the E2E profile's category name, e.g. `PROFILE_01`.
- **categoryLength**: Array size of **aCategory**.
- **aProfile**: The number of the profile, e.g. 22 if the category is `PROFILE_22`.
- **dataIDMode**: The data ID mode according to AUTOSAR (only available on PROFILE_01 and PROFILE_11).
  - Possible return values:
    - `DATAID_UNKNOWN = -1`
    - `DATAID_BOTH = 0`
    - `DATAID_ALT = 1`
    - `DATAID_LOW = 2`
    - `DATAID_NIBBLE = 3`
- **dataOffset**: Normalized bit position of the beginning of the payload over which the CRC is calculated, with respect to the complete PDU.
- **dataLength**: Length in bits of the payload over which the CRC is calculated.
- **crcOffset**: Normalized bit position of the beginning of the CRC, with respect to the complete PDU.
- **counterOffset**: Normalized bit position of the beginning of the Counter, with respect to the complete PDU.

## Return Values

- **0**: Successful
- **-1**: Not successful: PDU not found in database
- **-2**: Not successful: There is no signal group with the defined Name in the PDU or there is no E2E protection information defined for the signal group/PDU
- **-3**: Not successful: The array size of **aCategory** is too small

## Example

```plaintext
on PDU <PDU_NAME>
{
  char aCategory[100];
  long aProfile;
  long dataIDMode;
  long dataOffset;
  long dataLength;
  long crcOffset;
  long counterOffset;
  ARE2EGetProfileInfos (this, "", aCategory, elCount(aCategory), aProfile, dataIDMode, dataOffset, dataLength, crcOffset, counterOffset);
}
```
