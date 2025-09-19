[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetTxSAEnabled.md)

## EthernetMacsecSecureEntity::SetTxSAEnabled

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::SetTxSAEnabled

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Method Syntax

```plaintext
byte EthernetMacsecSecureEntity.SetTxSAEnabled(EthernetMacsecSCI sci, byte AN, uint8_t enabled);
```

### Description

Enables or disables use of an existing secure association for transmission.

Note that although more than one transmit SA may be enabled at the same time, only the last SA enabled will actually be used for transmission.

If the last transmit SA previously enabled will be disabled, the SecY will **not go back** to the second last enabled transmit SA. Errors will occur when trying to send Ethernet frames in this state.

Thus, to switch SAs, always obey the following order of operations:

- Enable first transmit SA
- Enabled second transmit SA
- The first transmit SA can now be disabled
- Enable third transmit SA
- The second transmit SA can now be disabled
- …

Note that a MKA server will cycle through association number 0..3 when rekeying; creating, enabling, disabling and deleting the transmit secure associations while signaling the receiving counterpart through MKA messages. The MKA server will leave the previous transmit secure association enabled, until the receiving participant signals that he is using the newly enabled transmit association's key for receiving on his side.

### Parameters

- **sci**: The secure channel id of the secure channel where this SA is part of.
- **AN**: The secure association number for the SA to be enabled or disabled.
- **enabled**: Specifies whether to enable or disable transmission for this SA.

### Return Values

- **byte**: 1 if the call succeeded, 0 otherwise.

The call will fail if:

- The secure channel referred to by the sci does not exist.
- The AN is not in range 0..3.

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
