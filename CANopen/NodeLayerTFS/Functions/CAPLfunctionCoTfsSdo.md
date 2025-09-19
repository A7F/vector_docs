# coTfsSDO (Level 3)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDO( dword index, dword subIndex );
```

## Description

This function executes the following transfers:

- [SDO Block Upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/PDOTests.md)
- [SDO Expedited Upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/ExpSdoUpload.md)
- [SDO Segmented Upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/SegSdoUpload.md)
- [SDO Block Download](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/BlockSdoDownload.md)
- [SDO Expedited Download](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/ExpSdoDownload.md)
- [SDO Segmented Download](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/SegSDODownload.md)

In each case, first a value is written with a download and this value is read back with an upload and checked. The test is destructive, the object in the DUT (Device Under Test) is overwritten. The object's data is overwritten during the test and not restored. The block transfers are transmitted with a CRC checksum if the CANopen® device supports these.

The test counts as passed if all 6 data transmissions were completed successfully.

## Parameters

- **index**: Index of a domain or string object.
- **subIndex**: Subindex of a domain or string object.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if ( coTfsSDO (0x2000, 0x0) != 1) {
  write("SDO test failed");
}
```
