[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetCKN.md)

## EthernetMacsecConfiguration::GetCKN

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecConfiguration::GetCKN

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

### Method Syntax

dword [EthernetMacsecConfiguration](../Objects/CAPLfunctionEthernetMacsecConfiguration.md).GetCKN(byte cak[]);

### Description

Copies the connectivity key name (CKN) of the given MACsec configuration into the byte array given as parameter.

### Parameters

- **cak[]**: A buffer where to copy the CKN.

### Return Values

- **dword**: The number of bytes copied into the specified byte array.

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
