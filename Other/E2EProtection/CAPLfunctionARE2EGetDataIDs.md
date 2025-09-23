# ARE2EGetDataIDs

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARE2EGetDataIDs (PDU * aPDU, char sigGroupName[], dword dataIDs[], dword dataIDLength, long & dataIDCount);
```

## Description

Returns the data IDs of a PDU with E2E protection. It is necessary that the PDU has a valid E2E.

## Parameters

- **aPDU**: A referenced PDU object.
- **sigGroupName**: The name of the signal group or empty. If empty, then the E2E should be directly defined at the PDU instead of the signal group.
- **dataIDs**: An array with all defined data IDs. Normally 1 or 16 values are returned.
- **dataIDLength**: Array size of data IDs.
- **dataIDCount**: The count of returned data IDs in the `dataIDs` array.

## Return Values

- **0**: Successful
- **-1**: Not successful: PDU not found in database
- **-2**: Not successful: There is no signal group with the defined Name in the PDU or there is no E2E protection information defined for the signal group/PDU
- **-3**: Not successful: Array of `dataIDs` is too small

## Example

```plaintext
on PDU <PDU_NAME>
{
  dword dataIDs[16];
  long dataIDCount;
  ARE2EGetDataIDs(this, "", dataIDs, elCount(dataIDs), dataIDCount);
}
```
