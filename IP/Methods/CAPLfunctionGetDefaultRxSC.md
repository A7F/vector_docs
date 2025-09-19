[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetDefaultRxSC.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetDefaultRxSC

# EthernetMacsecSecureEntity::GetDefaultRxSC

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

`byte EthernetMacsecSecureEntity.GetDefaultRxSC(EthernetMacsecSCI& sci);`

## Description

Returns the default secure channel used for receiving.

When receiving a MACsec frame without SCI (SC bit clear), and with ES bit clear, this secure channel will be used for decoding the MACsec frame.

Otherwise, the receive secure channel for decoding the MACsec frame will be determined from the MACsec frame’s content (SCI, or ES bit and source MAC address).

## Parameters

- **sci**: Returns the secure channel id of the secure channel used for receiving.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise. The call will fail if no secure channel has been created.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
