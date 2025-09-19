[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionUpdateMkaICV.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::UpdateMkaICV

# EthernetMacsecSecureEntity::UpdateMkaICV

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

[EthernetMacsecSecureEntity](../Objects/CAPLfunctionEthernetMacsecSecureEntity.md).UpdateMkaICV (ethernetPacket* packet);

## Description

Recalculates the integrity check value (ICV) of a MKPDU.

## Parameters

- **packet**: The packet for which to recalculate the ICV. The packet must be a valid MKA frame (MKPDU), conforming to IEEE802.1X.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
