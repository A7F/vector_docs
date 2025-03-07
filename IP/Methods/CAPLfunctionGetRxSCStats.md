[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetRxSCStats.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **EthernetMacsecSecureEntity::GetRxSCStats**

# EthernetMacsecSecureEntity::GetRxSCStats

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Method Syntax

```plaintext
byte EthernetMacsecSecureEntity.GetRxSCStats(EthernetMacsecSCI sci, MacsecSCReceiveStats& rxStats);
```

## Description

Returns the secure channel’s receive statistic variables.

## Parameters

- **sci**: The id of the secure channel to be queried.
- **rxStats**: Reference parameter where the receive statistics will be returned.

## Return Values

- **byte**: 1 if the call succeeded, 0 otherwise. Note that currently only the MACsec software implementation supports statistics according to IEEE802.1AE. The hardware secure entity will always return 0.

## Example

— 

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)