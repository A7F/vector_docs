[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetCipherSuites.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecConfiguration::GetCipherSuites

# EthernetMacsecConfiguration::GetCipherSuites

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

dword [EthernetMacsecConfiguration](../Objects/CAPLfunctionEthernetMacsecConfiguration.md).GetCipherSuites(qword cs[]);

## Description

Copies the currently configured cipher suite priority list of the given MACsec configuration into the qword array given as parameter. The single qwords are the cipher suite ids as specified in IEEE802.1X-2020.

## Parameters

- **cs[]**: A buffer where to copy the cipher suites.

## Return Values

- **dword**: The number of qwords, representing cipher suite ids, copied into the specified qword array.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
