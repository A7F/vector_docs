[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetConfidentialityOffset.md)

# EthernetMacsecSecureEntity::GetConfidentialityOffset

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetConfidentialityOffset

**Valid for**: CANoe DE

## Method Syntax

`byte EthernetMacsecSecureEntity.GetConfidentialityOffset(EthernetMacsecConfidentialityOffset& confOffset);`

## Description

Returns the currently agreed confidentiality offset. The value will be one of:

- **CONFIDENTIALITY_NONE** integrity protection without encryption will be used
- **CONFIDENTIALITY_OFFSET_0** encryption without offset
- **CONFIDENTIALITY_OFFSET_30, CONFIDENTIALITY_OFFSET_50** encryption with offset 30 or 50, respectively. Note that the XPN cipher suites do not support encryption with offset.

## Parameters

- **confOffset**: The reference parameter where the queried value will be returned.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

## Example

—
