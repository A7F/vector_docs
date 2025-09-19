[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetCapability.md)

# EthernetMacsecSecureEntity::GetCapability

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetCapability

**Valid for**: CANoe DE

## Method Syntax

`byte EthernetMacsecSecureEntity.GetCapability(EthernetMacsecCapability& capability);`

## Description

Returns the MACsec capability of the secure entity. Usually, this will be `MACSEC_CAP_INTEG_AND_CONF_0_30_50` (Integrity and Confidentiality with any offset). Future hardware PHY drivers may return one of the other values from `EthernetMacsecCapability`.

## Parameters

- **capability**: The reference parameter where the queried value will be returned.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
