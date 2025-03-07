[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetReplayProtection.md)

## EthernetMacsecSecureEntity::GetReplayProtection

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::GetReplayProtection

**Valid for**: CANoe DE

### Method Syntax

```plaintext
byte EthernetMacsecSecureEntity.GetReplayProtection(byte replayProtect, dword replayWindow);
```

### Description

Returns the replay protection settings. The parameter `replayProtect` indicates whether replay protection shall take place, `replayWindow` is the acceptable difference between the previous and the current frames’s packet numbers.

### Parameters

- **replayProtect**: The reference parameter where the queried value will be returned.
- **replayWindow**: The reference parameter where the queried value will be returned.

### Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)