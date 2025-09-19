# coTfsSDOBlockUpload (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDOBlockUpload( dword index, dword subIndex, dword useCrc, dword outCrcUsed[1] ); // form 1
long coTfsSDOBlockUpload( dword index, dword subIndex, dword useCrc, dword outSize[1], byte outValueBuf[], dword valueBufSize, dword outCrcUsed[1] ); // form 2
```

## Description

This function executes a complete [SDO block upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/PDOTests.md). The block transfer must be supported by the receiver. After a successful upload, the data received can be called up with the command [coTfsSDOGetUploadData](CAPLfunctionCoTfsSdoGetUploadData.md). (form 1)

Alternatively, the received data can be used as parameters directly and set whether the block transfer is executed with or without CRC support. (form 2)

A fallback to segmented transfer is not supported.

## Parameters

- **index**: Object index
- **subIndex**: Object subindex
- **useCrc**: Enables use of CRC check.
- **outSize[]**: Data size of the received data.
- **outValueBuf[]**: Data field with the received data.
- **valueBufSize**: Reception buffer size in byte of outValueBuf.
- **outCrcUsed[1]**: The passed CRC.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword dataLength, i;
byte pReceiveData[2048];
dword pOutCrcUsed[1];

if ( coTfsSDOBlockUpload(0x2002, 0, 1, pOutCrcUsed) != 1) {
  TestStepFail("SDO block upload test failed");
  return;
} // if
write ("show data received in previous step");

if ((dataLength = coTfsSDOGetUploadData( pReceiveData, 2048)) > 0) {
  write("datalength = %d, CRC used = %d",dataLength,pOutCrcUsed[0]);
  for (i = 0; i< dataLength; i++) {
    write("data %i = 0x%X",i,pReceiveData[i]);
  } // for
} // if
else {
  write("no data available");
} // else
```
