# coTfsSDOGetUploadSize (Level 1,2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

`dword coTfsSDOGetUploadSize( void );`

## Description

Provide the size of the transferred data after a SDO upload. This can be an [expedited](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/ExpSdoUpload.md), [segmented](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/SegSdoUpload.md) or [block](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/PDOTests.md) transfer.

## Parameters

—

## Return Values

Transfer size

## Example

See example of [coTfsSDOInit](CAPLfunctionCoTfsSdoInit.md)
