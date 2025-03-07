[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoGetUploadData.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsSDOGetUploadData**

# coTfsSDOGetUploadData (Level 1,2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsSDOGetUploadData( byte outValueBuf[], dword valueBufSize );
```

## Description

This function makes available the data of the last successful SDO upload procedure. This can be an [expedited](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/ExpSdoUpload.md), [segmented](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/SegSdoUpload.md) or [block](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/PDOTests.md) transfer.

The data field `outValueBuf` must always be able to accommodate the received data.

## Parameters

- **outValueBuf[]**  
  Received SDO upload data. Take care that this data field is of appropriate size depending on the use case!

- **valueBufSize**  
  Buffer size in byte of **outValueBuf**.

## Return Values

- **!0**  
  number of received bytes

- **0**  
  data not available or data buffer `outValueBuf` too small

## Example

See example of [coTfsSDOInit](CAPLfunctionCoTfsSdoInit.md)

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)