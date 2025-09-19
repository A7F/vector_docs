[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetIncludeSCI.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetIncludeSCI

# EthernetMacsecSecureEntity::GetIncludeSCI

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

`byte EthernetMacsecSecureEntity.GetIncludeSCI(byte& includeSCI);`

## Description

Returns preset for the SC flag in the tag control information (TCI). When this bit is set, MACsec frames will be sent including the SCI. Otherwise, no SCI will be sent.

## Parameters

- **includeSCI**: The reference parameter where the queried value will be returned.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
