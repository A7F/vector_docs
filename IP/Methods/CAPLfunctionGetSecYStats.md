[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetSecYStats.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetSecYStats

# EthernetMacsecSecureEntity::GetSecYStats

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

```plaintext
byte EthernetMacsecSecureEntity.GetSecYStats(EthernetMacsecSecYTransmitStats& txStats, EthernetMacsecSecYReceiveStats& rxStats);
```

## Description

Returns the secure entity's global transmit and receive statistic variables, according to IEEE802.1AE-2018.

See the IEEE802.1AE-2018, chapter 10.7, for thorough explanation of these statistics variables.

## Parameters

- **txStats**: Reference parameter where the transmit statistics will be returned.
- **rxStats**: Reference parameter where the receive statistics will be returned.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise. Note that currently only the MACsec software implementation supports statistics according to IEEE802.1AE. The hardware secure entity will always return 0.

## Example

—
