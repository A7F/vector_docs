# coTfsSDODownload (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDODownload( dword index, dword subIndex, dword size, byte inValueBuf[], dword valueBufSize ); // form 1
long coTfsSDODownload( dword index, dword subIndex, dword size, qword inValue); // form 2
```

## Description

This function makes available the complete SDO download functionality. It can be used in order to transfer data to the desired CANopen® device easily.

Form 1: Depending on the data length, either an [expedited](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/ExpSdoDownload.md) or [segmented](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/SegSDODownload.md) download is executed.

Form 2: This function syntax can only be used for [expedited](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/ExpSdoDownload.md) download.

## Parameters

- **index**: Object index
- **subIndex**: Object subindex
- **size**: Number of bytes to be transmitted.
- **inValueBuf[]**: Data field for transfer data.
- **valueBufSize**: Buffer size in byte of **inValueBuf**.
- **inValue**: Data to be transmitted.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSDODownload ( 0x1017, 0, 2, pdata, 2);
```
