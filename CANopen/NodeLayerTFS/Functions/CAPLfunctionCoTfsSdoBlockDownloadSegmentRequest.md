# coTfsSDOBlockDownloadSegmentRequest (Level 1)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsSDOBlockDownloadSegmentRequest( dword cont, dword seqNumber, byte inValueBuf[], dword valueBufSize, dword isLastSegment );
```

## Description

This function sends a single segmented [SDO block download](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/BlockSdoDownload.md) message and waits for the corresponding response.

## Parameters

- **cont**
  - 0: more segments will follow
  - 1: last segment
- **seqNumber**
  - Sequence number
- **inValueBuf[]**
  - Data field for transfer data
- **valueBufSize**
  - Buffer size in byte of `inValueBuf`
- **isLastSegment**
  - 0: more segments follow
  - 1: last segment of transmission

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

See example of [coTfsSDOGetBlockSize](CAPLfunctionCoTfsSdoGetBlockSize.md)
