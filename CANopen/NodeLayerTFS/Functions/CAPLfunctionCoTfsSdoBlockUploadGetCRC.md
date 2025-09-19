# coTfsSDOBlockUploadGetCRC (Level 1)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDOBlockUploadGetCRC( dword outValueBuf[] );
```

## Description

This function makes available the received CRC checksum of the last successful [SDO block upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/PDOTests.md) procedure.

## Parameters

- **outValueBuf[]**: Buffer to store the received CRC checksum.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

—
