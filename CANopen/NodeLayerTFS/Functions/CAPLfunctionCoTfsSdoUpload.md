[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoUpload.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsSDOUpload

# coTfsSDOUpload (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

- `long coTfsSDOUpload(dword index, dword subIndex); // form 1`
- `long coTfsSDOUpload(dword index, dword subIndex, dword outSize[1], byte outValueBuf[], dword valueBufSize); // form 2`
- `long coTfsSDOUpload(dword index, dword subIndex, dword outSize, qword outValueBuf); // form 3`

## Description

This function executes a complete SDO upload. Depending on the number of data, this is either an [expedited upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/ExpSdoUpload.md) (up to 4 bytes) or a [segmented transfer](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/SegSdoUpload.md). After a successful upload, the data received can be called up with the command [coTfsGetSdoUploadData](CAPLfunctionCoTfsSdoGetUploadData.md). (form 1)

Alternatively the function can return the received data automatically. (form 2)

This function syntax can only be used for [expedited uploads](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/ExpSdoUpload.md). (form 3)

## Parameters

- **index**: Object index
- **subIndex**: Object subindex
- **outSize[1]**: Data length pointer
- **outValueBuf[]**: Received data pointer
- **valueBufSize**: Buffer size in byte of **outValueBuf**.
- **outSize**: Size of the data to be transmitted.
- **outValueBuf**: Data to be transmitted.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword dataLength, i;
byte pReceiveData[2048];

if (coTfsSDOUpload(0x2000, 2) != 1) {
  write("SDO upload failed");
  return;
} // if

if ((dataLength = coTfsSDOGetUploadData(pReceiveData, 2048)) > 0) {
  write("datalength = %d", dataLength);
  for (i = 0; i < dataLength; i++) {
    write("data %i = 0x%X", i, pReceiveData[i]);
  } // for
} // if
else {
  write("no data available");
} // else
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)