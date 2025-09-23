[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetTxSCStats.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetTxSCStats

# EthernetMacsecSecureEntity::GetTxSCStats

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

`byte EthernetMacsecSecureEntity.GetTxSCStats(EthernetMacsecSCI sci, MacsecSCTransmitStats& txStats);`

## Description

Returns the secure channel’s transmit statistic variables.

## Parameters

- **sci**: The id of the secure channel to be queried
- **txStats**: Reference parameter where the transmit statistics will be returned.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise. Note that currently only the MACsec software implementation supports statistics according to IEEE802.1AE. The hardware secure entity will always return 0.

## Example

—
