[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetCurrentCipherSuite.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetCurrentCipherSuite

# EthernetMacsecSecureEntity::GetCurrentCipherSuite

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

byte [EthernetMacsecSecureEntity](../Objects/CAPLfunctionEthernetMacsecSecureEntity.md).GetCurrentCipherSuite(qword& cipherSuiteId);

## Description

Returns the ID of the currently agreed MACsec cipher suite. The value will be one of:

- CS_ID_GCM_AES_128        0x0080c20001000001
- CS_ID_GCM_AES_256        0x0080c20001000002
- CS_ID_GCM_AES_XPN_128    0x0080c20001000003
- CS_ID_GCM_AES_XPN_256    0x0080c20001000004
- CS_ID_NULL               0xFFFFFFFFFFFFFFFF (if non-MACsec traffic has been agreed upon by MKA)
- CS_ID_INVALID            0x0000000000000000 (cipher suite has not been initialized yet or MKA has not completed yet).

## Parameters

- **cipherSuiteId**: The reference parameter where the queried value will be returned.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

## Example

—  
Text

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
