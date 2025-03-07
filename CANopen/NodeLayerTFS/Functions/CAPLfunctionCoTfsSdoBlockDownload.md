[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoBlockDownload.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsSDOBlockDownload

# coTfsSDOBlockDownload (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDOBlockDownload( dword index, dword subIndex, dword size, dword useCrc, byte inValueBuf[], dword valueBufSize, dword outCrcUsed[] );
```

## Description

This function executes a complete [SDO block download](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/BlockSdoDownload.md). This function can be used to exchange simple larger quantities of data with a CANopen® device insofar as it supports the block transfer. A fallback to segmented transfer is not supported.

The parameter **useCrc** reports if a CRC check was executed during transmission.

## Parameters

- **index**: object index
- **subIndex**: object subindex
- **size**: number of bytes to be transmitted
- **useCrc**: reports if CRC check was executed during transmission
- **inValueBuf[]**: data field for transfer data
- **valueBufSize**: buffer size in byte of **inValueBuf**
- **outCrcUsed[]**: datafield, outCrcUsed[0] returns if a CRC check of the data was executed. This check can only be done if both sides of the communication (test module and test node) support CRC checks.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
byte pData[50];
dword outCrc[1];

// ... copy data to pData ...

if (coTfsSDOBlockDownload(0x2000, 0, 32, 1, pData, 50, outCrc) != 1) {
  TestStepFail("SDO block download test failed");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)