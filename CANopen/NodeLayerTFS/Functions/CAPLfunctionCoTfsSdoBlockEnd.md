[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoBlockEnd.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsSDOBlockEnd

# coTfsSDOBlockEnd (Level 1)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsSDOBlockEnd( dword ccs, dword cs, dword notUsed, dword crc ); // form 1
long coTfsSDOBlockEnd( dword ccs, dword cs, dword notUsed, dword crc, dword crcSetting ); // form 2
```

## Description

This function sends a SDO block end response/request message (depending on a [SDO block upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/PDOTests.md) and [SDO block download](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/BlockSdoDownload.md)) and awaits the corresponding response.

(2) The parameter `crcSetting` is used for [SDO block upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/PDOTests.md) only.

## Parameters

- **ccs (client command specifier)**
  - 5: block upload
  - 6: block download

- **cs (client subcommand)**
  - 1: end block download

- **notUsed**
  - Number of bytes in the last segment that contains no data.

- **crc**
  - CRC checksum, can be calculated with [coTfsCalcSdoCrc](CAPLfunctionCoTfsSdoCalcCrc.md), is 0 if client and/or server offer no CRC support.

- **crcSetting**
  - 0: no CRC support, the expected CRC is 0
  - 1: CRC is supported, the expected CRC must be specified in parameter `crc`
  - 2: no information about CRC support, received CRC are not evaluated, default setting for form 1

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

See example of [coTfsSDOBlockInit](CAPLfunctionCoTfsSdoBlockInit.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)