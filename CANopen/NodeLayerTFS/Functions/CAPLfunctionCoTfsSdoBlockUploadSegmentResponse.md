# coTfsSDOBlockUploadSegmentResponse (Level 1)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsSDOBlockUploadSegmentResponse( dword ccs, dword cs, dword ackSeq, dword blkSize, dword expMsgNumber, dword startSeqNumber );
```

## Description

This function waits for a SDO segmented [upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/PDOTests.md) request and sends the corresponding response. Before the call of this function, no time-delay functions should be inserted in order to prevent a loss of the request message.

## Parameters

- **ccs (client command specifier)**: 5: block upload
- **cs (client subcommand)**: 2: block upload response
- **ackSeq**: Sequence number of the message that should be confirmed.
- **blkSize**: Block size
- **expMsgNumber**: Number of requests awaited (generally corresponds to the value `ackSeq`), deviations can be used in order to provoke protocol violations.
- **startSeqNumber**: SDO block number of the first block expected.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

See example of [coTfsSDOBlockInit](CAPLfunctionCoTfsSdoBlockInit.md)
