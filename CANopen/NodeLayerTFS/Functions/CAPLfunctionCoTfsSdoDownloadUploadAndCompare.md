[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoDownloadUploadAndCompare.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsSDODownloadUploadAndCompare

# coTfsSDODownloadUploadAndCompare (Level 2)

[Feature availability for your product](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDODownloadUploadAndCompare( dword index, dword subIndex, dword size, qword downloadValue ); // form 1
long coTfsSDODownloadUploadAndCompare( dword index, dword subIndex, dword size, byte downloadValueBuf[], dword valueBufSize ); // form 2
```

## Description

This function executes a complete SDO download to write the object value and after that a SDO upload to read the written value. Depending on the number of data, this is either an [expedited upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/ExpSdoUpload.md) (up to 4 bytes) or a [segmented transfer](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/SegSdoUpload.md). Afterwards the received data is compared against the data supplied.

It is not possible to fetch the received data using [coTfsGetSdoUploadData](CAPLfunctionCoTfsSdoGetUploadData.md) after this function was called.

(2) can be used for maximum 4 byte objects only.

## Parameters

- **index**: Object index
- **subIndex**: Object subindex
- **size**: Expected data length.
- **downloadValue**: Value that is to be written.
- **downloadValueBuf[]**: Data pointer for data to be written.
- **valueBufSize**: Buffer size in byte of **downloadValueBuf**.

## Return Values

- [error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md) or
  - 0: data mismatch
  - 1: supplied data matches received data
  - 2: data length mismatch

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)